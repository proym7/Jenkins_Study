Jenkins Pipeline 구조
====================
>젠키스 파이프 라인에는 2가지 종류(Declarative Pipeline / Scripted Pipeline)가 있다.   
>오늘 알아볼 것은 Declarative Pipeline 이다. 

Pipeline 
--------
파이프라인을 사용하려면, 반드시 pipeline 을 포함해야한다.  
~~~
    pipeline {
        /* Declarative Pipeline 을 여기에 쓰면 된다 */
        
        agent any 
        
        parameters { 
            choice(choices: 'dq\live', description: '배포할 환경을 선택해주세요', name: 'ENV')
            }
        
        environment {
            REVISION = "latest"
            }

        stage('Deploy')
            {
              steps{
                script{
                    switch (ENV) {
                        case "dq": 
                            sh "dq.sh"
                            break
                        case "live": 
                            sh "live.sh"
                            break
                        }
                    }
                }
             }
     }
~~~

agent
-----
agent는 젠킨스 잡을 실행해줄 대상을 지정해 준다.   
agent의 parameter로는 any, none, label, node, docker, dockerile, kubernetes를 지원한다.   


parameter
-----------


environment
-----------


environment
-----------



참고 
--- 
>https://jenkins.io/doc/pipeline/examples/    
>https://jenkins.io/doc/book/pipeline/syntax/#agent
