# How to delete a list of users from Google Analytics via the Google Management API
A Python script that will delete a list of users from Google Analytics via the Google Management API. A typical use case for this would be for security purposes.



```import csv
import time
from retrying import retry
from apiclient.discovery import build
from oauth2client.service_account import ServiceAccountCredentials
import httplib2



def get_service(api_name, api_version, scope, key_file_location, service_account_email):

    # Parse command-line arguments.
    credentials = ServiceAccountCredentials.from_p12_keyfile(
        service_account_email, key_file_location, scopes=scope)

    http = credentials.authorize(http=httplib2.Http())

    # Build the service object.
    service = build(api_name, api_version, http=http)

    return service


with open('delete_ids.csv', 'rt') as csvfile:
    reader = csv.reader(csvfile, dialect='excel')
    reader_list = list(reader)
    for row in reader_list:
        print(row[0])


@retry

def delete_users(service):
    for row in reader_list:
        service.management().accountUserLinks().delete(
        accountId ='43334570',
        linkId = row[0]
        ).execute()
        print(str(row[0]) + ' has been deleted')
        time.sleep(60)


def main():
    # Define the auth scopes to request.
    scope = ['https://www.googleapis.com/auth/analytics.manage.users']
    service_account_email = 'user-management@x-sell-betfair-1.iam.gserviceaccount.com'
    key_file_location = 'client_secrets.p12'

    # Authenticate and construct service.
    service = get_service('analytics', 'v3', scope, key_file_location, service_account_email)
    delete_users(service)


if __name__ == '__main__':
    main()```
