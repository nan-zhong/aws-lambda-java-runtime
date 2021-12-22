FROM rabbitsign/graalvm-native-image:latest
ENV JAR_PATH build/libs
ENV JAR_NAME aws-lambda-java-dynamodb-native-0.0.1-SNAPSHOT-all
COPY ${JAR_PATH}/${JAR_NAME}.jar /home/application/
COPY bootstrap /home/application/
WORKDIR /home/application
RUN ${GRAALVM_HOME}/bin/native-image --verbose -jar ${JAR_NAME}.jar
RUN mv ${JAR_NAME} function
RUN chmod 777 function
RUN zip -j function.zip bootstrap function
ENTRYPOINT ["bash"]