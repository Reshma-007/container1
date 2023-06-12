// pipeline {
//     agent any

//     stages {
//     //    stage('Checkout') {
//     //        steps {
//     //             Checkout your source code repository
//     //            git branch: 'master', credentialsId: 'e5cb28bb-e658-4ac5-aa81-9f9ac7d7cabc', url: 'https://gitlab.com/Reshma-007/ci_cd.git'
//     //        }
//     //    }
        
//        stage('Build Docker Image') {
//             steps {
//                 // Build Docker image
//                 script {
//                     // Build the Docker image
//                     sh 'docker build -t https://gitlab.com/Reshma-007/ci_cd:jenpy .'
                    
//                     // Optionally, tag the Docker image with a specific version
//                     sh 'docker tag jenpy jenpy_0.1'
                    
//                     // Push the Docker image to a registry
//                     sh 'docker push https://gitlab.com/Reshma-007/ci_cd:jenpy_0.1'
//                 }
//             }
//         }
//     }
// }


// pipeline {
//     agent any

//     stages {
    //     stage('Checkout') {
    //         steps {
    //             // Checkout your source code repository
    //             git branch: 'master', credentialsId: 'your-gitlab-credentials-id', url: 'https://gitlab.com/your-username/your-repo.git'
    //         }
    //     }
        

        //----------------------------------------------------------------------
//         stage('Build Docker Image') {
//             steps {
//                 // Build Docker image using the Dockerfile in the repository
//                 script {
//                     def dockerImage = docker.build('python:python', '-f Dockerfile .')
//                    // sh 'docker inspect --format="{{.Id}}" ${dockerImage.id}'
//                    // sh "docker inspect --format='{{.Id}}' ${dockerImage.id}"    //if we don give tag, then imageId will be displayed.
//                 }
//             }
//         }

//         stage('Push Docker Image') {
//             steps {
//                 script {
//                     // Login to the GitLab container registry
//                     docker.withRegistry('https://gitlab.com/Reshma-007/ci_cd/container_registry', '75b46a6d-0097-47ba-bb01-f1887e7ab5f8')
//                     sh 'docker push python:python'
//                     //{
//                         // Push the Docker image to the registry
//                         //dockerImage.push()
//                 //}
                    
//                 }
//             }
//         }
//     }
// }
// ---------------------------------------------------------------------------------------------------------------


pipeline {
    agent any
    // environment {
    //     GITLAB_TOKEN=credentials('gitlab-token')
    // }

    stages {
        stage('Build Docker Image') {
            steps {
                script {
                    sh 'docker build -t python1:python1 -f Dockerfile .'
                }
            }
        }

        stage('loginto gitlabContainerRegistry'){
            steps{
                script{
                   // sh 'echo glpat-MBymA9B8bV3rnxQWyTyY | docker login -u Reshma-007 --password-stdin https://gitlab.com/'
                    sh 'docker login -u reshma-007 -p Eesha@007 https://gitlab.com'
                    // sh ' docker login -u gitlab+deploy-token-2140202 --password-stdin https://gitlab.com'
                }
            }
        }
        stage('PushBuildImage'){
            steps{
                     sh 'docker push https://gitlab.com/reshma-007/ci_cd/python1:python1'
                    //sh 'docker push registry.gitlab.com/reshma-007/ci_cd:python1'
                }
            }                 
    }
}