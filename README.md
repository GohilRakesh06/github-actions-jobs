    v A workflow run is made up of one or more jobs, which run in parallel by default. To run jobs sequentially, you can define dependencies on other jobs using the jobs.<job_id>.needs keyword
    v Each job runs in a runner environment specified by runs-on.
    v Setting id for a job
        ○ use jobs.<job_id> to set unique identifier for job
        jobs:
  my_first_job:
    name: My first job
  my_second_job:
    name: My second job
    v Defining prerequisits for jobs
        ○ Use jobs.<job_id>.needs to identify any jobs that must complete successfully before this job will run. It can be a string or array of strings. If a job fails or is skipped, all jobs that need it are skipped unless the jobs use a conditional expression that causes the job to continue.
        jobs:
  job1:
  job2:
    needs: job1
  job3:
    needs: [job1, job2]
        ○ in above job1 must complete sucessfully before job2 begins, job3 waits for both job1 and  job2.
        
    
