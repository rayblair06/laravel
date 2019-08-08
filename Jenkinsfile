node {
    stage('preparation') {
        // Checkout the master branch of the Laravel framework repository
        git branch: 'master', url: 'https://github.com/rayblair06/laravel.git'
    }
    
    stage("composer_install") {
        // Run `composer update` as a shell script
        sh 'composer install'
    }
    
    stage("phpunit") {
        // Run PHPUnit
        sh 'vendor/bin/phpunit'
    }
    
    stage("laravel migration") {
        sh 'php artisan migrate'
    }
}
