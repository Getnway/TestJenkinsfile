properties([[$class: 'BuildDiscarderProperty', strategy: [$class: 'LogRotator', artifactDaysToKeepStr: '', artifactNumToKeepStr: '', daysToKeepStr: '', numToKeepStr: '10']]]);

node {
    stage('Checkout') {
        checkout scm
    }
    stage('Build'){
    	echo 'build'
    }
    stage('Test'){
        echo 'test'
    }
    stage('Deploy'){
        withCredentials([sshUserPrivateKey(credentialsId: "GetnwayId", keyFileVariable: 'keyfile')]) {
            echo '#!/bin/bash'>restart.sh
            echo 'cd /data/texas/api-server'>>restart.sh
            echo 'sh run.sh -r'>>restart.sh
            sh "ssh root@iwintv.com bash<restart.sh"
        }
    }
}
