## AIX 서버에서 다른 서버로 Syslog를 보낼때 설정 방법
#### Syslog.conf. 파일에서 Syslog전송 서버 설정
```
#] vi /etc/syslog.conf
*.* @192.168.10.111          //192.168.10.111 로 모든 로그 전송이며 입력은 'Facility.Priority @전송 서버IP'(IP앞에 @표기 필요) 내용을 뜻함.
#] refresh -s syslogd        //변경된 Syslog 설정 적용
```
#### Facility(로그 유형) 설명
1) kern : 커널 메세지
2) mail : 메일 시스템 메세지
3) user : 사용자 레벨 메세지
4) daemon : 시스템데몬 메세지
5) auth : 보안, 인증 메세지
6) syslog : syslogd데몬 메세지
7) lpr : line printer 서브시스템 메세지
8) news : 뉴스 서브시스템 메세지
9) uucp : uucp 서브시스템 메세지
10) cron : 크론 데몬 메세지
11) caa : 클러스터 인식 AIX 서브시스템
12) local0 ~ local7 : 로컬 사용을 위해 예약
13) * : 모든 Facility

#### Priority(로그 등급) 설명
1) emerg : 시스템 패닉으로 인한 메세지
2) alert : 조치를 즉시 수행 필요
3) crit : 심각한 메세지
4) err : 에러 메세지
5) warning : 경고메세지
6) notice : 중요 메세지
7) info : 일반적인 정보 메세지
8) debug : 디버깅 레벨 메세지
