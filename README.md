passing secrets to a docker container:

a. a string through a command line interface
b. supply a file with enviromental variables



retrieval API secret key from aws:



    aws kms create-key --description <key-name> --region <region>

    sample:
                    aws kms create-key --description keyname --region us-east-1
                {
                    "KeyMetadata": {
                        "AWSAccountId": "538417891515",
                        "KeyId": "bfa5483b-917d-45c0-9350-779da45151a2",
                        "Arn": "arn:aws:kms:us-east-1:538417891515:key/bfa5483b-917d-45c0-9350-779da45151a2",
                :...skipping...
                {
                    "KeyMetadata": {
                        "AWSAccountId": "538417891515",
                        "KeyId": "bfa5483b-917d-45c0-9350-779da45151a2",
                        "Arn": "arn:aws:kms:us-east-1:538417891515:key/bfa5483b-917d-45c0-9350-779da45151a2",
                        "CreationDate": "2020-10-16T12:05:24.205000+02:00",
                        "Enabled": true,
                        "Description": "keyname",
                        "KeyUsage": "ENCRYPT_DECRYPT",
                        "KeyState": "Enabled",
                        "Origin": "AWS_KMS",
                        "KeyManager": "CUSTOMER",
                        "CustomerMasterKeySpec": "SYMMETRIC_DEFAULT",
                        "EncryptionAlgorithms": [
                            "SYMMETRIC_DEFAULT"
                        ]
                    }
                }



    aws ssm put-parameter --name MY-NASA-API-KEY --value "<secret-value>" --type SecureString
                --key-id "<your-key-id>" --region <region>

    sample:
    aws ssm put-parameter --name MY-NASA-API-KEY --value "NhllfUSvmKmdzgrUr8bdrwYBsM0ttbXvVuh1Be9u" --type SecureString \
                --key-id "bfa5483b-917d-45c0-9350-779da45151a2" --region us-east-1
