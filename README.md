# getIP
REM Get and store your external IP

REM Add a timer to keep track over an extended period of time

REM Store output in a database

@echo off

@set d=%date:~10,4%%date:~4,2%%date:~7,2%%time:~0,2%%time:~3,2%%time:~6,2%

@set d=%d: =0%

for /F %%I in ('curl -s https://api.my-ip.io/ip.txt') do set ip=%%I

echo %d%,%ip%>> ip.txt
