node {
    
    git branch:'master', url:'git@github.com:manumilou/gitlab-ci-example-asciidoc.git'
    
    docker.image('rochdev/alpine-asciidoctor:mini').inside {
        stage "html"
        sh "asciidoctor analyse.adoc"
        // Archive the build output artifacts.
        archiveArtifacts artifacts: 'analyse.html'
        stage "pdf"
        sh "asciidoctor-pdf -a pdf-stylesdir=resources -n -a pdf-style=sfl analyse.adoc"
        // Archive the build output artifacts.
        archiveArtifacts artifacts: 'analyse.pdf'
    }
}
