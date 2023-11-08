node{
    stage("clone"){
        git branch: 'main', url: 'https://github.com/arjun-adangadhavan/sample-java-spring-app.git'
        sh "ls"
    }
    stage("compile"){
        sh "mvn clean install"
    }
    stage("image"){
        sh "docker build -t dante97/java-app ."
        sh "docker images"
    }
    stage("dockerhub"){
        sh "docker login -u dante97 -p Arjun1997//"
        sh "docker push dante97/java-app"
    }
    stage("dockercontainer"){
        sh "docker rm -f java-app"
        sh "docker run -d -p 8081:8080 --name=java-app dante97/java-app"
    }
    stage("clean"){
        cleanWs()
    }
}
