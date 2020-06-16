## curl学习

1. 通过ftp下载文件
+ 使用内置option：-o(小写)
    ```
    # curl -o dodo1.jpg http:www.linux.com/dodo1.JPG
    ```
+ 使用内置option：-O（大写)
    ```
    # curl -O http://www.linux.com/dodo1.JPG
    ```
    这样就会以服务器上的名称保存文件到本地

+ 循环下载

    有时候下载图片可以能是前面的部分名称是一样的，就最后的尾椎名不一样
    ```
    # curl -O http://www.linux.com/dodo[1-5].JPG
    ```
    这样就会把dodo1，dodo2，dodo3，dodo4，dodo5全部保存下来
+ 下载重命名
    ```
    # curl -O http://www.linux.com/{hello,bb}/dodo[1-5].JPG
    ```
    由于下载的hello与bb中的文件名都是dodo1，dodo2，dodo3，dodo4，dodo5。因此第二次下载的会把第一次下载的覆盖，这样就需要对文件进行重命名。
    ```
    # curl -o #1_#2.JPG http://www.linux.com/{hello,bb}/dodo[1-5].JPG
    ```
    这样在hello/dodo1.JPG的文件下载下来就会变成hello_dodo1.JPG,其他文件依此类推，从而有效的避免了文件被覆盖
+ 分块下载

    有时候下载的东西会比较大，这个时候我们可以分段下载。使用内置option：-r
    ```
    # curl -r 0-100 -o dodo1_part1.JPG http://www.linux.com/dodo1.JPG
    # curl -r 100-200 -o dodo1_part2.JPG http://www.linux.com/dodo1.JPG
    # curl -r 200- -o dodo1_part3.JPG http://www.linux.com/dodo1.JPG
    # cat dodo1_part* > dodo1.JPG
    ```
    这样就可以查看dodo1.JPG的内容了

+ curl可以通过ftp下载文件，curl提供两种从ftp中下载的语法
    ```
    # curl -O -u 用户名:密码 ftp://www.linux.com/dodo1.JPG
    # curl -O ftp://用户名:密码@www.linux.com/dodo1.JPG
    ```
+ 显示下载进度条
    ```
    # curl -# -O http://www.linux.com/dodo1.JPG
    ```
+ 不会显示下载进度信息
    ```
    # curl -s -O http://www.linux.com/dodo1.JPG
    ```
+ 断点续传

    在windows中，我们可以使用迅雷这样的软件进行断点续传。curl可以通过内置option:-C同样可以达到相同的效果
如果在下载dodo1.JPG的过程中突然掉线了，可以使用以下的方式续传
    ```
    # curl -C -O http://www.linux.com/dodo1.JPG
    ```
+ 上传文件

    curl不仅仅可以下载文件，还可以上传文件。通过内置option:-T来实现
    ```
    # curl -T dodo1.JPG -u 用户名:密码 ftp://www.linux.com/img/
    ```
    这样就向ftp服务器上传了文件dodo1.JPG

2. 使用cookie

+ 很多网站都是通过监视你的cookie信息来判断你是否按规矩访问他们的网站的，因此我们需要使用保存的cookie信息。内置option: -b

    ```
    # curl -b cookiec.txt http://www.linux.com
    ```

+ 保存http的response里面的cookie信息。内置option:-c（小写）
    ```
    # curl -c cookiec.txt  http://www.linux.com
    ```
    执行后cookie信息就被存到了cookiec.txt里面了
+ 保存http的response里面的header信息。内置option: -D
    ```
    # curl -D cookied.txt http://www.linux.com
    ```
    执行后cookie信息就被存到了cookied.txt里面了

    注意：-c(小写)产生的cookie和-D里面的cookie是不一样的。

3. 模仿浏览器

    有些网站需要使用特定的浏览器去访问他们，有些还需要使用某些特定的版本。curl内置option:-A可以让我们指定浏览器去访问网站
    ```
    # curl -A "Mozilla/4.0 (compatible; MSIE 8.0; Windows NT 5.0)" http://www.linux.com
    ```
