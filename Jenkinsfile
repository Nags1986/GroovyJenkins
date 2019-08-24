#!/usr/bin/env groovy
import hudson.model.*
import hudson.EnvVars
import java.net.URL

node('myslave'){
    stage('Git checkout'){
        git 'https://github.com/edureka-git/DevOpsClassCodes.git'
    }
    stage('Compile Addressbook'){
        withMaven(maven:'myMaven'){
            sh 'mvn compile'
        }
    }
    stage('Package Addressbook'){
        withMaven(maven:'myMaven'){
            sh 'mvn package'
        }
        
    }
}
