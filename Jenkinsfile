#!/bin/bash
node('master') {
    stage("Récupère le Code Source") {
        git 'https://github.com/luyenge/lesson5.git'
    }
    
    dir('Lesson5') {
        printMessage('Pipeline encours d-execution')
        stage("Testing") {
           // #sh "python test_functions.py"
            python test_functions.py
        }
        stage("Deploiement") {
            if (env.BRANCH_NAME == 'master') {
                printMessage('La branche master encours de Dépoiement')
            } else {
                printMessage("Pas de Déploiement pour la branche [${env.BRANCH_NAME}]")
            }
            
        }
        printMessage('Pipeline Terminé')
    }
}

def printMessage(message) {
    echo "${message}"
}
