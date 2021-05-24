# iOS_development_tips
> ios 앱개발 진행하면서 참고할 팁 정보 저장소 

<details><summary>ADHoc 배포 과정 정리(드롭박스)</summary>
<p>

1. 프로비저닝 프로파일에 기기 등록 해서 다운로드
2. 드롭박스에 plist 및 ipa 업로드 후 공유 설정 및 공유 주소 복사
3. dl.dropboxusercontent.com/s/주소/app.ipa 로 변환 -> plist에 입력
4. dl.dropboxusercontent.com/s/주소/manifest.plist 로 변환 -> html에 입력
5. html 파일 구성 
```html
<a href="itms-services://?action=download-manifest&url=https://dl.dropboxusercontent.com/s/주소/manifest.plist">iOS Install</a>
```
6. http://dl.dropboxusercontent.com/s/주소/index.html 로 주소 전달 진행
</p>
</details>

