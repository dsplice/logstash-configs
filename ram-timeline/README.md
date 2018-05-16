# RAM Timeline


git clone https://github.com/superponible/volatility-plugins.git ~/files/


docker run --rm -it -v ~/files:/data blacktop/volatility -f ram-image.raw --profile=Win7SP1x64 timeliner --output=body > time.txt

docker run --rm -it -v ~/files:/data blacktop/volatility -f ram-image.raw --profile=Win7SP1x64 shellbags --output=body >> time.txt

docker run --rm -it -v ~/files:/data blacktop/volatility -f ram-image.raw --profile=Win7SP1x64 mftparser --output=body >> time.txt

docker run --rm -it -v ~/files:/data blacktop/volatility --plugins=volatility-plugins -f ram-image.raw --profile=Win7SP1x64 firefoxcookies --output=body >> time.txt

docker run --rm -it -v ~/files:/data blacktop/volatility --plugins=volatility-plugins -f ram-image.raw --profile=Win7SP1x64 firefoxdownloads --output=body >> time.txt

docker run --rm -it -v ~/files:/data blacktop/volatility --plugins=volatility-plugins -f ram-image.raw --profile=Win7SP1x64 firefoxhistory --output=body >> time.txt

docker run --rm -it -v ~/files:/data blacktop/volatility --plugins=volatility-plugins -f ram-image.raw --profile=Win7SP1x64 chromecookies --output=body >> time.txt

docker run --rm -it -v ~/files:/data blacktop/volatility --plugins=volatility-plugins -f ram-image.raw --profile=Win7SP1x64 chromedownloads --output=body >> time.txt

docker run --rm -it -v ~/files:/data blacktop/volatility --plugins=volatility-plugins -f ram-image.raw --profile=Win7SP1x64 chromehistory --output=body >> time.txt


grep -v ^Volatility time.txt > time2.txt

mactime –b time2.txt -d > time3.txt

grep -v ^Date time3.txt > timeline.csv

sed -i 's/Xxx Xxx 00 0000 00:00:00/Thu Jan 01 1970 00:00:00/' timeline.csv

rm time.txt time2.txt time3.txt timeline.txt
