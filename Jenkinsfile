#!/usr/bin/env groovy
import hudson.model.*
import hudson.EnvVars
import java.net.URL

node('myslave'){
    stage('Git checkout the code'){
        git 'https://github.com/edureka-git/DevOpsClassCodes.git'
    }
    stage('Compile the Addressbook code'){
        withMaven(maven:'myMaven'){
            sh 'mvn compile'
        }
    }
    stage('Package Addressbook code to war'){
        withMaven(maven:'myMaven'){
            sh 'mvn package'
        }
        
    }
}
