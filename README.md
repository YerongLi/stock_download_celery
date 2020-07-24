# A股日线行情数据异步下载器

基于Tushare和Celery的日线行情数据异步下载器。

需要先前往 tushare.com 注册用户。

目前仅支持日线数据，欢迎补充。

## 使用：

安装依赖:

```
pip install -r requirements.txt
```

启动 mongodb:

```
mongodb
```

启动 worker:

```
python -m celery worker -A tasks -l info --pool=eventlet
```

修改tasks.py中26行的token为你自己用户对应的tushare token.

调整downloader.py中的日期为你需要的数据区间。

运行downloader.py，下发任务，此时可以看到worker进程开始执行任务：

```
python downloader.py
```

