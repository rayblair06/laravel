node {    
    stage("composer_install") {
        // Composer Install
        sh 'composer install --no-interaction --prefer-dist --optimize-autoloader'
    }
    
    stage("phpunit") {
        // Run PHPUnit
        sh 'vendor/bin/phpunit'
    }
    
    stage("migrations") {
        sh 'php artisan migrate --force'
    }
    
    stage("build assets") {
        sh 'php artisan migrate --force'
        
        sh 'rm -fr public/images'
        sh 'rm -fr public/css'
        sh 'rm -fr public/js'
        sh 'yarn'
        sh 'npm run prod'
    }
}
