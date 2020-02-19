## Data Binding in Spring

- Command Objects (aka Backing Beans)
    - Are used to transfer data to and from web forms
- Spring will automatically bind data of form posts
- Binding done by property name (less 'get'/'set')

- Example of a 'PersonBean'
    - 'firstName' would bind to property firstName
    - 'address.addressLine1' would bind to the addressLine1 
    one of the address property of the PersonBean
    - email[0]/email[1] would bind to index zero and one of the email 
    List or Set property of Person
