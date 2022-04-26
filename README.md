# iOS_development_tips
> ios 앱개발 진행하면서 참고할 팁 정보 저장소 

<details><summary>ADHoc 배포 과정 정리(드롭박스)</summary>
<p>

1. 프로비저닝 프로파일에 기기 등록 해서 다운로드
2. 드롭박스에 plist 및 ipa 업로드 후 공유 설정 및 공유 주소 복사
3. dl.dropboxusercontent.com/s/주소/app.ipa 로 변환 -> plist에 입력
4. menifest.plist 구성
```xml
<?xml version="1.0" encoding="UTF-8"?>
<!DOCTYPE plist PUBLIC "-//Apple//DTD PLIST 1.0//EN" "http://www.apple.com/DTDs/PropertyList-1.0.dtd">
<plist version="1.0">
<dict>
  <key>items</key>
	<array>
		<dict>
			<key>assets</key>
			<array>
				<dict>
					<key>kind</key>
					<string>software-package</string>
					<key>url</key>
					<string>https://dl.dropboxusercontent.com/s/주소/app.ipa</string>
				</dict>
			</array>
			<key>metadata</key>
			<dict>
				<key>bundle-identifier</key>
				<string>(앱아이디)</string>
				<key>bundle-version</key>
				<string>(버전)</string>
				<key>kind</key>
				<string>software</string>
				<key>title</key>
				<string>(앱이름)</string>
			</dict>
		</dict>
	</array>
</dict>
</plist>
```
5. dl.dropboxusercontent.com/s/주소/manifest.plist 로 변환 -> html에 입력
6. index.html 파일 구성 
```html
<!DOCTYPE HTML>  
<html>  
<head>  
  <meta name="viewport" content="user-scalable=no, width=device-width, initial-scale=1.0, maximum-scale=1.0"/>
  <meta name="apple-mobile-web-app-capable" content="yes" />

  <title>OTA Ad-Hoc 설치 페이지</title>
  <style>
    li {margin: 10px;}
  </style>
</head>  
<body>  
  <ul>
    <li><p>iOS 1.0.1</p></li>
    <li><a href="itms-services://?action=download-manifest&url=https://dl.dropboxusercontent.com/s/주소/manifest.plist">App Install</a></li>
  </ul>
</body> 
</html>
```
6. http://dl.dropboxusercontent.com/s/주소/index.html 로 주소 전달 진행
</p>
</details>

<details><summary>Device Support</summary>
<p>
https://github.com/filsv/iPhoneOSDeviceSupport
	
https://github.com/iGhibli/iOS-DeviceSupport
	
/Applications/Xcode.app/Contents/Developer/Platforms/iPhoneOS.platform/DeviceSupport/ 경로에 붙여넣기.
</p>
</details>

<details><summary>Documentation</summary>
<p>

```sh
jazzy --min-acl internal 
--clean 
--xcodebuild-arguments -workspace,{PRODUCT_NAME}.xcworkspace,-scheme,{PRODUCT_NAME}
```

</p>
</details>

