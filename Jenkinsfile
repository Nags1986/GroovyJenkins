#!/usr/bin/env groovy
import hudson.model.*
import hudson.EnvVars
import java.net.URL

node{
    stage('Git checkout the code'){
        git 'https://github.com/edureka-git/DevOpsClassCodes.git'
    }
    stage('Compile the checked out code'){
        withMaven(maven:'myMaven'){
            sh 'mvn compile'
        }
    }
    stage('Package the compiled code to war'){
        withMaven(maven:'myMaven'){
            sh 'mvn package'
        }
        
    }
}
