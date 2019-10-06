# 在Mac上使用GPG签名

## use brew install
  `brew install gpg`
  
  `brew upgrade gnupg`
  
  `brew install pinentry-mac`
  
  `echo "pinentry-program /usr/local/bin/pinentry-mac" >> ~/.gnupg/gpg-agent.conf`
  
  `killall gpg-agent`
## 测试安装是否成功（需要先进行生成密钥）

  `echo "test" | gpg --clearsign`
  
  这时候应该会弹出GUI界面让你输入密码
  
  如果此测试成功(没有错误/输出包括PGP签名)

# 常用GPG命令

## 生成GPG密钥
  `gpg --full-generate-key`

## 列出所有GPG密钥
  `gpg --list-secret-keys --keyid-format LONG`

## 导出GPG密钥
  `gpg --armor --export {GPGKEYID}`

# GIT 自动签名设置
  `git config --global user.signingkey {GPGKEYID}`
  
  `git config --global commit.gpgsign true`
