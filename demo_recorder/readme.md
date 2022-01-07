# 命令行录制套件

用于录制演示git命令的工具组件，基于docker启动一个纯净的ubuntu环境，终端为zsh。  

录制使用开源工具[asciinema](https://github.com/asciinema/asciinema)。

## 使用方式

```shell
# cd demo_recorder
docker build . -t demo_recorder
docker run -it --rm -v $PWD:/root/recorder demo_recorder 
# 在启动的命令行中进行录制，环境中已经包含git、vim
```

![示例](/demo_recorder/img/demo.gif)

```shell
# cd demo_recorder
# 使用该命令将录制的命令转换为GIF
docker run --rm -v $PWD:/data asciinema/asciicast2gif  cast/rewrite_history rewrite_history.gif 
# 该容器默认不包含中文字体，存在中文需要手动挂载字体目录
docker run --rm -v $PWD:/usr/share/fonts/custom_fonts  -v $PWD:/data asciinema/asciicast2gif  cast/rewrite_history rewrite_history.gif 
```

> 录制之前注意将终端窗口调整到合适大小
