# appointment

## This is a simple project only for Login and Simple Appointment Based on Taro and wechat-mini-program

Current project fontend is based on taro 4.1.9. It is necessary to confirm `npm >=16.20.0 ` ; the backend is compiled and run on **JDK 21**

## folder structure
- appintment (fontend part. backed on react)
- TaroDemo (backend part. based on JAVA)

## How to Run Fontend - Taro + wechat-mini-app
1. cd to `appointment`
2. run command `yarn` to install the modules.
3. run the command `yarn dev:weapp` to test on the wechat-mini-program or run the command `yarn build:weapp` to package files.
4. run the [wechat-developer-tools](https://developers.weixin.qq.com/miniprogram/dev/devtools/download.html) to import the project from the path `dist`

###  Developers need to pay attention to the project settings of the developer tools：
Need to set off ES6 to ES5 function,turn on may lead to error
Need to set off the style auto-completion when uploading code, turn on may lead to error
Need to set off the code compression upload, turn on may lead to error

## How to RUN Backend - JAVA + Spring Boot
1. cd to TaroDemo
2. run command `gradle clean build` 
3. the jar package named `appointment-service.jar` generated under the path `build/libs`
4. run the command `java -jar appointment-service.jar`. The service will be started on port 8888.

### backend components
I use the following components:
- Spring Boot Web as a simple web server
- Caffeine as the progress based cache 
- MyBatis as the DB dialect generator
- MyBatis Flex as the enhancement tool of MyBatis

server runs on the port 8888 by default. 
DB schema name is TaroDemo

## How to verify the appointment flow
1. First time open the wechat-mini-program, we need to have a simplify login.
  - enter any phone number start, clieck `发送验证码`
  - a mock sms code 123456 could be used to login.
  - click `登录` to login the appointment system

2. If the session is not expired, we won't login again
3. Dashboard page is appointment list.
  - click `发起新预约` to add a new appointment.
  - long press appointment item could delete the appointment

4. On the Appoint page, Subject , date, starttime and endtime is all necessary to input
5. Click `保存预约` to save the new appointment, and return back to list page.
