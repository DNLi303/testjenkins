#基于 `microsoft/dotnet:1.0.0-core` 来构建我们的镜像
FROM microsoft/dotnet:2.1-aspnetcore-runtime


#设置时区
RUN /bin/cp /usr/share/zoneinfo/Asia/Shanghai /etc/localtime && echo 'Asia/Shanghai' >/etc/timezone
#拷贝项目publish文件夹中的所有文件到 docker容器中的publish文件夹中  
COPY . /publish

#设置工作目录为 `/publish` 文件夹，即容器启动默认的文件夹
WORKDIR /publish

#设置Docker容器对外暴露8888端口
EXPOSE 8062

#使用`dotnet HelloWebApp.dll`来运行应用程序

CMD ["dotnet", "WebApplication1.dll", "--server.urls", "http://*:8062"]