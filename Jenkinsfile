pipeline {
	agent any
	stages {
		stage("build") {
			steps {
				echo 'building the applicaiton...'
			}
		}
		stage("test") {
			steps {
				echo 'testing the applicaiton...'
			}
		}
		stage("deploy") {
			steps {
				echo 'deploying the applicaiton...'
			}
		}
	}
    pipeline {
	agent any
	stages {
		stage("build") {
			when {
                expression {
                    env.GIT_BRANCH == 'origin/main'
                }
            }
            steps {
                echo 'building the applicaitoan...'
            }
		}
		stage("test") {
			when {
                expression {
                    env.GIT_BRANCH == 'origin/test' || env.GIT_BRANCH == ''
                }
            }
            steps {
                echo 'testing the applicaiton...'
            }
		}
		stage("deploy") {
			steps {
				echo 'deploying the applicaiton...'
			}
		}
	}
    post {
        always {
            echo 'building..'
        }
        success {
            echo 'success'
        }
        failure {
            echo 'failure'
        }
    }
}
}