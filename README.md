# ds-워드프레스
워드프레스용 docker-compose입니다.<br>
NPM 뒤 리버스프록시로 사용하기 적합합니다.<br>

## 사용방법
<strong>
git clone https://github.com/ablokr/wordpress-ab.git<br>
cd wordpress-ab<br>
vi docker-compose.yml  // DB root 계정 및 사용자 계정 수정<br>

![image](https://user-images.githubusercontent.com/107911055/180369543-c2e586bb-6b2e-4860-a4c1-15ea74e2f62c.png)

sudo chown -R 82:82 ./data/wordpress  // PHP 실행계정인 www-data의 UID/PID로 변경<br>
sudo docker-compose up -d <br>
</strong><br>

![image](https://user-images.githubusercontent.com/107911055/180369964-1f1b9924-e2f4-4613-b42a-d337256e21dc.png)


## 특징
### Nginx 1.22

<strong>
- nginx 설정값 - ./config/nginx/nginx.conf<br>
- wordpress 설정값 - ./config/nginx/default.conf<br>
- nginx webroot ./data/wordpress<br>
- nginx log ./data/log/nginx<br>
</strong>  
  
<br>
*HTTP/2(서버 푸시 포함)<br>
*BoringSSL(Google의 OpenSSL 풍미)<br>
*0-RTT를 지원하는 TLS 1.3<br>
*브로틀리 압축<br>
*headers-more-nginx-module<br>
*NJS<br>
*nginx_cookie_flag_module<br>
*JIT 컴파일 이 활성화된 최신 PCRE<br>
*최신 zlib<br>
*알파인 리눅스(총 10MB 압축)<br>

Nginx 1.22 - https://github.com/woosungchoi/docker-nginx-brotli 로 NPM(Nginx Proxy Manager)로 사용하게끔 직접 빌드하였습니다.
<br>
### PHP7.4-fpm 
<strong>
- PHP 설정값 - ./config/php/php.ini</strong><br>
<br>
ffmpeg 및 기타 확장과 함께 빌드되었습니다.
### MariaDB
<strong>
- DB설정값 ./data/config/db/my.cnf </strong><br>
Mariadb 최신버전<br>
<br>

### Redis
Cache를 위한 Redis - W3 Total과 같은 Cache 플러그인과 사용가능.


