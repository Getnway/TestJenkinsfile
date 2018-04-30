properties([[$class: 'BuildDiscarderProperty', strategy: [$class: 'LogRotator', artifactDaysToKeepStr: '', artifactNumToKeepStr: '', daysToKeepStr: '', numToKeepStr: '10']]]);

node {
	echo 'Checkout'
    stage('Checkout') {
        checkout scm
    }
	echo 'Build'
    stage('Build'){
    	echo 'build'
    }
	echo 'Test'
    stage('Test'){
        echo 'test'
    }
	echo 'Deploy'
    stage('Deploy'){
        withCredentials([sshUserPrivateKey(credentialsId: "GetnwayId", keyFileVariable: 'keyfile')]) {
            echo '#!/bin/bash'>restart.sh
            echo 'cd /data/texas/api-server'>>restart.sh
            echo 'sh run.sh -r'>>restart.sh
            sh "ssh root@iwintv.com bash<restart.sh"
        }
    }
	echo 'end'
}
