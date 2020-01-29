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
                                    execCommand: "ip a"
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
