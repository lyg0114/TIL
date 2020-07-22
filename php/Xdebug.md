# Mac에서 xdebug로 디버깅 하자
- pear 설치
    >curl -O https://pear.php.net/go-pear.phar<br>
     sudo php -d detect_unicode=0 go-pear.phar

     1. 1번 선택
     2. /usr/local/pear 입력
     3. 4번 선택
     4. /usr/local/bin 입력
     5. 엔터 입력
     6. pear version --> 설치완료 확인

 - xdebug 설치
  >pecl install xdebug    

 - /etc/php.ini 에다가 경로 설정
    >zend_extension="/usr/lib/php/extensions/no-debug-non-zts-20160303/xdebug.so" <br>
    xdebug.remote_enable = 1 <br>
    xdebug.remote_autostart = 1<br>



### xDebug 설치할때 발생하는 문제 해결법 
- php 버전과 xdebug의 버전이 맞지않아 발생하는 오류인 줄 알았지만 아니었다.
- mojave 의 문제였음<br>

https://bbqsoftwares.com/blog/xdebug-catalina-issue
>/private/tmp/pear/install/xdebug/xdebug.c:25:10: fatal error: 'php.h' file not found
#include "php.h"<br>
1 error generated.<br>
make: *** [xdebug.lo] Error 1<br>
ERROR: `make' failed<br>


# 


## 번외

- homebrew 설치 https://osxdaily.com/2018/03/07/how-install-homebrew-mac-os/

- autoConf 설치 https://gist.github.com/anunay/7698181

