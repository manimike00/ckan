pipeline {
    agent any
    stages {
        stage('Build') {
            steps {
                script {
                        sshPublisher(
                            publishers: [
                                sshPublisherDesc(
                                configName: "ckan",
                                transfers: [
                                sshTransfer(
                                    execCommand: "cd ~/ckan && git pull origin develop && ansible-playbook playbook.yml"
                                ),
                                sshTransfer(
                                    execCommand: "echo 'logged succesfully'"
                                )
                            ])
                        ])
                }
            }
        }
    }
}
