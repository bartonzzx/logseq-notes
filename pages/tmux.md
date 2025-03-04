# 参考
- [tmux教程-阮一峰](https://www.ruanyifeng.com/blog/2019/10/tmux.html)
- # 配置
- ## 重新载入配置
- ```bash
  tmux source-file ~/.tmux.conf
  ```
- ## 启用vi快捷键模式
- 修改~/.vim.conf，增加以下内容
- ```bash
  setw -g mode-keys vi
  ```
- ## 启用插件管理tpm
- ```bash
  git clone https://github.com/tmux-plugins/tpm ~/.tmux/plugins/tpm
  ```
- ## 启用tmux-yank插件
- 将tmux缓冲区的内容直接复制到系统剪切板
- 在~/.vim.conf增加内容，在tmux内使用Prefix + I 自动配置插件，在copy mode下选择好内容后，按y复制
- ```bash
  # 启用插件管理器
  set -g @plugin 'tmux-plugins/tpm'
  set -g @plugin 'tmux-plugins/tmux-yank'
  
  # 初始化插件管理器
  run '~/.tmux/plugins/tpm/tpm'
  ```