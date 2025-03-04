# 参考
- [菜鸟教程docker命令](https://www.runoob.com/docker/docker-command-manual.html)
- # 解决failed to initialize NVML
- ## 参考
- [Failed to initialize NVML: Unknown Error in Docker ](https://stackoverflow.com/questions/72932940/failed-to-initialize-nvml-unknown-error-in-docker-after-few-hours)
- ## 方法
- ``` bash
  Change config.toml in nvidia-container-runtime:
  sudo vim /etc/nvidia-container-runtime/config.toml
  then changed no-cgroups = false, save
  Restart docker daemon: 
  sudo systemctl restart docker
  ```
- ## 分析
- ### **1. `no-cgroups` 参数的作用**
- `no-cgroups` 是 `nvidia-container-runtime` 配置文件中的一个选项，用于控制是否在容器中禁用 cgroup（Control Group）。cgroup 是 Linux 内核提供的一种机制，用于限制、记录和隔离进程组的资源使用（如 CPU、内存、GPU 等）。
- 如果 `no-cgroups = true`，NVIDIA 容器运行时会尝试绕过 cgroup 的管理，这可能导致 GPU 资源无法正确分配给容器。
- 如果 `no-cgroups = false`，NVIDIA 容器运行时会遵循 Docker 的 cgroup 配置，从而确保 GPU 资源能够被正确分配和管理 
  
  在此场景中，将 `no-cgroups` 设置为 `false` 后，NVIDIA 容器运行时开始与 Docker 的 cgroup 配置协同工作，解决了 NVML 初始化失败的问题。
- ### **2. 为什么需要重启 Docker 守护进程？**
- 修改 `config.toml` 文件后，必须重启 Docker 守护进程以使更改生效。这是因为 Docker 在启动时会读取配置文件并初始化相关的运行时环境。如果不重启 Docker，新的配置不会被加载，问题仍然存在
- 通过执行以下命令：`sudo systemctl restart docker`
- Docker 会重新加载配置，并确保 NVIDIA 容器运行时使用更新后的 `no-cgroups` 设置。
- # 解决docker pull/push代理问题
- ## 参考
- [docker设置代理](https://neucrack.com/p/286)
- [docker pull代理设置](https://docs.docker.com/reference/cli/docker/image/pull/#proxy-configuration)：包含多种设置代理的方法，由于linux一般使用docker cli，转至下方链接
- [docker cli代理设置](https://docs.docker.com/reference/cli/dockerd/#proxy-configuration)：介绍多种在docker cli下配置代理的方法，由于设置了systmd host docker，所以转至下方链接
- [docker daemon代理设置](https://docs.docker.com/engine/daemon/proxy/#daemon-configuration)：注意分清default mode和rootless mode
- ## 注意
- 在`/etc/systemd/system/docker.service.d/http-proxy.conf`中，切记`[Service]`的写法，Service首字母大写:(   (debug it for 45 min)