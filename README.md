对该[博客](https://ittousei.github.io) 进行的修改

部署的时候 `Gemfile.lock` 文件要添加
参照https://ruby-china.org/topics/41719
``` lock
PLATFORMS
  aarch64-linux
  aarch64-linux-gnu
  aarch64-linux-musl
  arm-linux
  arm-linux-gnueabihf
  arm-linux-musleabihf
  arm64-darwin
  x86-linux
  x86-linux-gnu
  x86-linux-musl
  x86_64-darwin
  x86_64-linux
  x86_64-linux-gnu
  x86_64-linux-musl
```
部署步骤参照https://github.com/cotes2020/jekyll-theme-chirpy/issues/667#issuecomment-1250194442

If you have a problem similar to the following: 
 - My Github Actions stuck in Queued status
   see https://github.com/actions/runner/issues/3300#issue-2308231807