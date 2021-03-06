## Endless searching and downloading Repo 

[More Info](https://github.com/hardikvasa/google-images-download/issues/7#issuecomment-372079102)

install selenium

`pip install selenium`

install geckodriver driver 
download driver
`wget https://github.com/mozilla/geckodriver/releases/download/v0.18.0/geckodriver-v0.18.0-linux64.tar.gz`
unpack driver
`tar -xvzf geckodriver*`
executable
`chmod +x geckodriver`
set path
`export PATH=$PATH:/path-to-extracted-file/geckodriver`

use scroll flag to define the scrolling range by pixel and the download-pool range. simply run

`python google-images-download.py --keywords "Neil Armstrong, nasa astronaut neil armstrong, apollo neil armstrong" --max 500 --scroll 200 --thread 6 --type face` optional laso `--proxy ip:port` for proxy and `--verbose 3` for debug.


```
('-k', '--keywords', help='delimited list input', type=str, required=True)
('-o', '--output', help='output directory', type=str, required=False)
('-u', '--unique', help='create always new sub unique folder', type=bool, required=False, default=False)
('-m', '--max', help='maximal download images', type=int, required=False, default=1000)
('-t', '--thread', help='download workers range', type=int, required=False, default=6)
('-s', '--scroll', help='scroll range', type=int, required=False, default=1000)
('-ch', '--chips', help='chips string', type=str, required=False)
('-p', '--proxy', help='proxy ip:port', type=str, required=False)
('-y', '--type', help='search image type', type=str, required=False, choices=['face', 'clipart', 'photo', 'lineart', 'animated'])
('-c', '--color', help='filter on color', type=str, required=False, choices=['red', 'orange', 'yellow', 'green', 'teal', 'blue', 'purple', 'pink', 'white', 'gray', 'black', 'brown'])
('-v', '--verbose', action="store", help="0:Error, 1:Warning, 2:INFO*(default), 3:debug", default=2, type=int)
```

```
python google-images-download.py --keywords "tom hanks" --max 200 --scroll 200 --thread 10
INFO:__main__:Saving Files in ~/data/raw_downloaded_image/tom hanks
INFO:__main__:Starting Download Process...
INFO:__main__:thread Thread 0 did 0 images
INFO:__main__:thread Thread 1 did 0 images
INFO:__main__:thread Thread 3 did 0 images
INFO:__main__:thread Thread 1 did 1 images
INFO:__main__:thread Thread 0 did 1 images
...
...
INFO:__main__:thread Thread 3 did 47 images
INFO:__main__:tearDown
INFO:__main__:kill <Process(Process-2, started)>
INFO:__main__:close pool <multiprocessing.pool.Pool object at 0x7fb78d364b38>
INFO:__main__:takes ~70.16436553001404 seconds for 200 images



python google-images-download.py --keywords "tom hanks" --max 20 --scroll 200 --thread 4
INFO:__main__:thread Thread 0 did 0 images
INFO:__main__:thread Thread 2 did 0 images
INFO:__main__:thread Thread 1 did 0 images
INFO:__main__:thread Thread 2 did 1 images
INFO:__main__:thread Thread 1 did 1 images
INFO:__main__:thread Thread 0 did 1 images
INFO:__main__:thread Thread 0 did 2 images
INFO:__main__:thread Thread 3 did 0 images
INFO:__main__:thread Thread 3 did 1 images
INFO:__main__:thread Thread 1 did 2 images
INFO:__main__:thread Thread 0 did 3 images
INFO:__main__:thread Thread 1 did 3 images
INFO:__main__:thread Thread 2 did 2 images
INFO:__main__:thread Thread 3 did 2 images
INFO:__main__:thread Thread 0 did 4 images
INFO:__main__:thread Thread 3 did 3 images
INFO:__main__:thread Thread 0 did 5 images
INFO:__main__:thread Thread 1 did 4 images
INFO:__main__:thread Thread 3 did 4 images
INFO:__main__:tearDown
INFO:__main__:kill <Process(Process-2, started)>
INFO:__main__:close pool <multiprocessing.pool.Pool object at 0x7f6735d37b00>
INFO:__main__:takes ~7.96940803527832 seconds for 20 images
INFO:__main__:thread Thread 0 did 6 images


```
