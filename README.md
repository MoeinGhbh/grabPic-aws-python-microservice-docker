passing secrets to a docker container:

a. a string through a command line interface
b. supply a file with enviromental variables



retrieval API secret key from aws:

    ssm = boto3.client('ssm', region_name='us-east-1')
    response = ssm.get_parameters(Names=['MY_NASA_API_KEY'],
                                  WithDecryption=True)
    nasa_api_key = response['Parameters'][0]['Value']