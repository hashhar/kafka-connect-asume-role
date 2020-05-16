# Kafka Connect Assume Role

This is a Kafka Connect plugin that adds support for assuming IAM roles using
AWS STS (Security Token Service). This can then be used to interact with any
AWS service that the assumed IAM role has a permission for.

The motivation to create this was to enable easy usage of cross-account IAM
roles for accessing AWS services in a different account.

Please feel free to file bugs and provide patches.

## Using

Add this as a dependency in your project using the Maven co-ordinates below.

```xml
<dependency>
    <groupId>com.hashhar.kafka.connect.auth</groupId>
    <artifactId>kafka-connect-assume-role</artifactId>
    <version>0.1.0</version>
</dependency>
```

This JAR should be present in the classpath of your Kafka Connect workers to
make sure that this works.

## Building

```sh
git clone https://github.com/hashhar/kafka-connect-assume-role.git
cd kafka-connect-assume-role
mvn clean verify
```

## Configuration

```sh
<prefix>.class=com.hashhar.kafka.connect.auth.AwsStsCredentialsProvider
<prefix>.role_arn=arn:aws:iam::012345678901:role/my-role
<prefix>.role_session_name=my-session-name
<prefix>.external_id=my-optional-external-id
```

