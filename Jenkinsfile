#!/usr/bin/env groovy
import hudson.model.*
import hudson.EnvVars
import java.net.URL

node{
    stage('Git checkout the code'){
        git 'https://github.com/Nags1986/DevOpsClassCodes.git'
    }
    
    stage('Compile the checked out code'){
        withMaven(maven:'myMaven'){
            sh 'mvn compile'
        }
    }
    
    stage('review the compiled code'){
        withMaven(maven:'myMaven'){
            sh 'mvn pmd:pmd'
        }
    }
    
    stage('Test the reviewed code'){
        withMaven(maven:'myMaven'){
            sh 'mvn test'
        }
    }
    
    stage('Coverage check the Tested code'){
        withMaven(maven:'myMaven'){
            sh 'mvn cobertura:cobertura -Dcobertura.report.format=xml'
        }
    }
    
    stage('Package the final code to .war'){
        withMaven(maven:'myMaven'){
            sh 'mvn package'
        }
        
    }
}
