# LeanovateHeliosRecipient
Tridium Niagara Custom Alarm Recipient to interface with Helios Ticketing System
Explanation of key sections:

Imports and Annotations: The code begins with several import statements, importing classes required for various functionalities. The @NiagaraType annotation indicates that this class is associated with the Niagara framework.

Constants and Configuration: Several constants and configuration parameters are defined at the beginning of the class. These include the user agent, username and password for authentication, URLs for sending GET and POST requests to the Freshdesk API, and various status and error codes.

sendGET Method: This method sends a GET request to the Freshdesk API to retrieve information about existing tickets. It sets up a connection, adds necessary headers (such as User-Agent and Authorization), and handles the response accordingly.

searchTicket Method: This method searches for an existing ticket based on the given pointName. It is similar to the sendGET method but focuses on searching for tickets with a specific point name.

sendPOST Method: This method sends a POST request to the Freshdesk API to create a new ticket. It constructs a JSON payload containing ticket information (such as email, description, subject, etc.), adds the necessary headers, and sends the request.

handleAlarm Method: This method is overridden from the BAlarmRecipient class and is called when an alarm is triggered. It processes the alarm record, checking if it's in a normal or alarm state. If in a normal state, it attempts to search for an existing ticket and update its status. If in an alarm state, it creates a new ticket using the sendPOST method.

Note: The code seems to lack some comments and error handling, which might be essential for production use. Additionally, the use of the javax.xml.bind.DatatypeConverter class suggests that this code is using Java 8 or earlier. For Java 9 and later, a different approach for Base64 encoding/decoding should be used.
