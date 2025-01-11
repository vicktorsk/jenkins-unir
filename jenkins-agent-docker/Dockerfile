FROM jenkins/inbound-agent as agent

FROM alpine:3.19

RUN apk -U add openjdk17-jre git make

COPY --from=agent /usr/local/bin/jenkins-agent /usr/local/bin/jenkins-agent
COPY --from=agent /usr/share/jenkins/agent.jar /usr/share/jenkins/agent.jar

ENTRYPOINT ["/usr/local/bin/jenkins-agent"]