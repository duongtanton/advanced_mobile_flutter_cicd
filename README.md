# advanced_mobile_flutter_cicd

This is a project for cicd with flutter.

## Getting Started

This project is a starting point for a Flutter application using cicd to build, test and release. 
If you want to implement cicd for your flutter project, you can use this project as a template 
and flow the steps below.

1. Create a new flutter project <a href="https://docs.flutter.dev/get-started/codelab">here</a>:

2. Config your project follow the steps <a href="https://docs.flutter.dev/deployment/android">here</a>:
   - Important step: You must sign your app follow <a href="https://docs.flutter.dev/deployment/android#sign-the-app">here</a>. 

3. Config your repository to build, test and release follow the steps bellow:
    - Add environment secrets: https://github.com/username/repo-name/settings/secrets/actions
        - Add `KEYSTORE_BASE64` secret: 
          - cmd: base64 -i <path-to-file-keystore> -w 0. Then copy the result and paste to secret value.
        - Add `STORE_PASSWORD` secret:
          - The password of your keystore file.
        - Add `KEY_PASSWORD` secret:
          - The password of your key in keystore file.
        - Add `KEY_ALIAS` secret:
          - May be is: upload, you can check it in the document.
        - Add `PLAYSTORE_ACCOUNT_KEY` secret:
          - This secret is used to upload your app to play store. Get in google play console.
        - Add `SLACK_WEBHOOK` secret:
          - Guide: https://www.svix.com/resources/guides/how-to-get-slack-webhook-url/ 
    - To enable the job release tag and push to store you must uncomment the code in `.github/workflows/android-release.yml` file.
3. Trigger the workflow to build, test and release your app.
    - You can trigger the workflow by push code or pull request to main/beta/testing branch with commit or pull message is always contain "Version: x.y.z".
    - You can check and change with your requirement, the workflow status in: .github/workflows/android-release.yml

## References
    - https://blog.logrocket.com/flutter-ci-cd-using-github-actions/ 
    - https://docs.flutter.dev/deployment/android#sign-the-app
## Do by
    ### HCMUS - Phát triển ứng dụng cho thiết bị di động nâng cao - 20_3 - Group 26.
    - Dương Tấn Tồn - 20120598
    - Trần Trọng Đại - 20120449
    - Thái Nguyễn Viêt Hùng - 20120488