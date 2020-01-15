stage 'Checking connectivity'
node {
    deleteDir()
    checkout scm
    
    wrap([$class: 'AnsiColorBuildWrapper', colorMapName: "xterm"]) {
        ansiblePlaybook(
            playbook: 'ping.yml',
            inventory: 'init.ini',
            credentialsId: '',
            colorized: true)
    }
}

stage "Check syntax"
node {
    wrap([$class: 'AnsiColorBuildWrapper', colorMapName: "xterm"]) {
        ansiblePlaybook(
            playbook: 'renew.yml',
            inventory: 'init.ini',
            credentialsId: '',
            extras: '--syntax-check',
            colorized: true
            )
    }
}

stage "Check dry-run"
node {
    wrap([$class: 'AnsiColorBuildWrapper', colorMapName: "xterm"]) {
        ansiblePlaybook(
            playbook: 'renew.yml',
            inventory: 'init.ini',
            credentialsId: '',
            extras: '--check --diff',
            colorized: true
            )
    }
}

stage "Deploy to production"
node {
    wrap([$class: 'AnsiColorBuildWrapper', colorMapName: "xterm"]) {
        ansiblePlaybook(
            playbook: 'renew.yml',
            inventory: 'init.ini',
            credentialsId: '',
            colorized: true
            extras: '--diff'
            )
    }
}


stage "Deploy to System & Hardening"
node {
    wrap([$class: 'AnsiColorBuildWrapper', colorMapName: "xterm"]) {
        ansiblePlaybook(
            playbook: 'playbook.yml',
            inventory: 'prod.ini',
            credentialsId: '',
            colorized: true
            extras: '--diff'
            )
    }
}