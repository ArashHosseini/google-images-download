## Endless searching and downloading Repo 

The main process(collector) has to look for links and collect them, then the workers(download_worker) take care of the pool for the download. We need selenium to "scroll down" and get the hidden nodes. The process will run until keyboard interruption or if the items len in output folder rich the max value.

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