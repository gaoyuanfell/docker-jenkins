pipeline {
    agent{
        label 'master'
    }
    stages {
	    //拉取git代码仓库
        stage('git check out') {
            steps {
                git branch: 'master', credentialsId: 'dd7cf7ff-e6be-43b6-bf8f-c3c98ab0ad4c', url: 'git@github.com:gaoyuanfell/docker-auto-release.git'
            }
        }
        //下载依赖、编译安装
        stage('npm build') {
            steps {
                //下载依赖
                sh 'npm i'
                //编译安装 npm run test 这个是test环境的打包命令
                sh 'npm run build'
            }
        }
    }
}