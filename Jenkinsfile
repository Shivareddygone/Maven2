@Library("mylibrary")_
node("built-in")
{
    stage('ContDownload_Loans')
    {
        cicd.newgit("maven.git")
    }
    stage('ContBuild_Loans')
    {
        cicd.newMaven()
    }
    
 }
