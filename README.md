@echo off
set ADB_PATH="C:\Program Files\TxGameAssistant\ui\adb.exe"
set DEVICE_ID=emulator-5554

%ADB_PATH% kill-server
%ADB_PATH% start-server

%ADB_PATH% -s %DEVICE_ID% shell stop logd
%ADB_PATH% -s %DEVICE_ID% shell pm trim-caches 8192M
%ADB_PATH% -s %DEVICE_ID% shell settings put system user_refresh_rate 120
%ADB_PATH% -s %DEVICE_ID% shell wm density 320

echo.
echo Optimizasyon islemleri emulator-5554 icin tamamlandi.
pause
