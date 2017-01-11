# JenkinsAPI
JenkinsAPI URL commands

echo "job-2 is running"
Job_1_Build_Number=$(curl http://192.168.0.82:8080/job/job-1/lastStableBuild/buildNumber --user raja:3f7f75096dsaeaafea968bca5dacf71cc)
Job_1_Project="job-1"
Job_1_Build_Status=$(curl http://192.168.0.82:8080/job/job-1/lastBuild/api/json?pretty=true --user raja:3f7f7509638dasewafaa5dacf71cc | grep result | awk -F'"' '{$0=$4}1')
x=$(curl http://192.168.0.82:8080/job/job-1/lastBuild/api/json?pretty=true --user raja:3f7f7509adaeafa5dacf71cc | grep timestamp | awk '{print $3}' | sed 's/,$//')
Job_1_Time=$(date -d @$x)



echo "Job_1_Build_Status: ${Job_1_Build_Status}"
echo "Project: ${Job_1_Project}"
echo "Job_1_Build_URL: ${JENKINS_URL}job/${Job_1_Project}/${Job_1_Build_Number}"
echo "Job-1_Build_Number: ${Job_1_Build_Number}"
echo "Time started: ${Job_1_Time}"


echo ${JENKINS_URL}
