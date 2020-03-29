Jenkins Pipeline 구조
====================
>젠키스 파이프 라인에는 2가지 종류(Declarative Pipeline / Scripted Pipeline)가 있다.   
>오늘 알아볼 것은 Declarative Pipeline 이다. 

Pipeline 
--------
pipeline 안에 꼭 선언되어야 한다.   
~~~
    pipeline {
        /* insert Declarative Pipeline here */
    }
~~~

agent
-----
agent의 parameter로는 any, none, label, node, docker, dockerile, kubernetes를 지원한다. 


참고 
--- 
>https://jenkins.io/doc/pipeline/examples/    
>https://jenkins.io/doc/book/pipeline/syntax/#agent
