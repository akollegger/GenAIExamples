

## Docker on EC2

:IMPORTANT: hardware requirements:
- 120GiB storage
- 32GiB RAM
- tested on AWS EC2 `m7i-flex.2xlarge` which eventually stopped responding
- upgraded to AWS EC2 `m7i-flex.8xlarge` :fingers_crossed:


1. Follow along with the [Step-by-Step Guide to Install Docker on Amazon Linux machine in AWS](https://medium.com/@srijaanaparthy/step-by-step-guide-to-install-docker-on-amazon-linux-machine-in-aws-a690bf44b5fe)


2. Get git: `sudo yum install git -y`

3. Clone the example: `git clone https://github.com/opea-project/GenAIExamples.git`

4. Also, install docker compose manually, not the yum'my way... [docker compose linux](https://docs.docker.com/compose/install/linux/)

5. Recommended, save env variables in .bash_profile rather than just for session. Instead of copy/pasting IP address, consider using `IP_ADDR=$(curl -s http://whatismyip.akamai.com/)`

6. Otherwise follow along: https://github.com/opea-project/GenAIExamples/tree/main/ChatQnA


### Troubleshooting

1. If tgi-service fails to you may not have enough disk or RAM. 

Some messages are obscure, like this one which is the result of insufficient RAM:
```
ERROR text_generation_launcher: Download process was signaled to shutdown with signal 9: 
Error: DownloadError
```

See: https://github.com/huggingface/text-generation-inference/issues/451

2. If the EC2 instance appears to freeze (the terminal becomes unresponsive), you may need a bigger instance
