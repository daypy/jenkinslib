#!groovy

@Library('jenkinslib') _
def tools = new org.devops.tools()

pipeline{
    //指定运行此流水线的节点
    agent { node { label "master"}}
    
	environment {
		activeEnv = 'dev'
	}

    //流水线的阶段
    stages{

        //阶段1 获取代码
        stage("CheckOut"){
            steps{
                script{
                    println("获取代码")
					println("${activeEnv}")
                }
            }
        }
        stage("Build"){
            steps{
                script{
                    println("运行构建")
                }
            }
        }
		
		//代码扫描
		stage("CodeScan"){
			steps{
				timeout(time:30, unit:"MINUTES"){
					script{
						println("代码扫描")
						tools.PrintMes("this is my lib!!!")
					}
				}
			}
		}
    }
    post {
        always{
            script{
                println("流水线结束后，经常做的事情")
            }
        }
        
        success{
            script{
                println("流水线成功后，要做的事情")
            }
        
        }
        failure{
            script{
                println("流水线失败后，要做的事情")
            }
        }
        
        aborted{
            script{
                println("流水线取消后，要做的事情")
            }
        
        }
    }
}
