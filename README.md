---

## 🛠 Homebrew 설치

1. [Homebrew 공식 사이트](https://brew.sh/index_ko) 접속  
2. 설치 커맨드 복사 후 터미널 실행  
3. 에러 발생 시 해결 (`Warning: /opt/homebrew/bin is not in your PATH`)

```bash
cd /opt
# homebrew 폴더 유무 확인 (없으면 생성)
sudo mkdir homebrew
sudo chown -R $(whoami) /opt/homebrew

# 설치
curl -L https://github.com/Homebrew/brew/tarball/master | tar xz --strip 1 -C homebrew

# 환경변수 추가
echo 'export PATH=/opt/homebrew/bin:$PATH' >> ~/.zshrc
source ~/.zshrc

# 설치 확인
brew --version


🐘 PHP 8 설치
brew tap shivammathur/php
brew install shivammathur/php/php@8.1
brew link --overwrite --force php@8.1
brew services restart shivammathur/php/php@8.1

# 환경변수 추가
echo 'export PATH="/opt/homebrew/opt/php@8.0/bin:$PATH"' >> ~/.zshrc
echo 'export PATH="/opt/homebrew/opt/php@8.0/sbin:$PATH"' >> ~/.zshrc
source ~/.zshrc

# 설치 확인
php -v


📦 Composer 설치
brew install composer
composer help


composer global require "laravel/installer"
composer global require laravel/installer --update-with-all-dependencies

# valet 설치
composer global require laravel/valet
valet install


✅ Laravel 프로젝트 생성 테스트
cd your_project_directory
composer create-project laravel/laravel blog "8.*"
php artisan


🗄 MariaDB 설치
brew update
brew install mysql

# 실행/종료/상태 확인
mysql.server start
mysql.server stop
mysql.server status

# 접속
mysql -uroot -p

❗ root 계정 에러 발생 시
sudo mysql -u root -p
set password=password('1234');

