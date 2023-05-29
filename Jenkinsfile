pipeline {
    agent any
    stages {       
        stage('git') {
              steps {
                git branch: 'main', url: 'https://github.com/JD100gb/Jai_Jenkins.git'
            }
        }
         stage('deploy on Remote Server (http://13.233.112.233/1029)') {
            steps {
                sshPublisher(publishers: [sshPublisherDesc(configName: 'LinuxWebServer', transfers: [sshTransfer(cleanRemote: false, excludes: '', execCommand: '', execTimeout: 120000, flatten: false, makeEmptyDirs: false, noDefaultExcludes: false, patternSeparator: '[, ]+', remoteDirectory: '/var/www/html/1029', remoteDirectorySDF: false, removePrefix: '', sourceFiles: '**/**')], usePromotionTimestamp: false, useWorkspaceInPromotion: false, verbose: false)])
            }
        }
         stage('Hello') {
            steps {
                echo 'Hello World'
            }
        }
    }
}
