pipeline {
  agent any
  stages {
    stage('git') {
      steps {
        dir(path: '/home/shiyanlou/Code') {
          git(url: 'git@github.com:xiongzhihang/test_jenkins.git', branch: 'main', credentialsId: '	23b4b2d8-55b9-49d1-93ee-f5557eef2bd5')
        }

      }
    }

    stage('build') {
      steps {
        sh 'pip3 install -r requirements.txt'
      }
    }

    stage('run') {
      steps {
        sh 'uwsgi --http 0.0.0.0:8001 --wsgi-file u.py --callable app --daemonize true'
      }
    }

  }
}