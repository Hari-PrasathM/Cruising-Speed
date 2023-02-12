# Cruising-Speed
import requests

# Define the channel ID and read API key
channel_id = "2030597"
read_api_key = "20Z31EOVYNP4XBEM"
b='90'
c='90'
# Define the URL for the GET request
url = "https://api.thingspeak.com/channels/{}/fields/2.json?api_key={}".format(channel_id, read_api_key)

# Make the GET request
response = requests.get(url)

# Check the status code of the response to make sure the request was successful
if response.status_code == 200:
    # Get the JSON data from the response
    data = response.json()

    # Access the data from the response
    feeds = data["feeds"]
    for feed in feeds:
        # print("Timestamp: {}".format(feed["created_at"]))
        a="{}".format(feed["field2"])
        if a>="80" && <="90":
            print("Yay! ECONOMIC")
        if a==b==c:
            print("You are maintaining constant speed")
        
        print(a)
        c=b
        b=a

else:
    print("Request failed with status code {}".format(response.status_code))
