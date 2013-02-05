# SSLExport

Simple command-line tool for exporting non-SSL services as SSL services on another interface

For instance, to export a MongoDB SSL connection, and make local connections to
port 8080 go to my.other.server:443, you'd create a config file `sslexport.ini`:  

    [sslexport]
    pemfile=/path/to/pem/file
    external=my.public.ip.address
    
    [sslexport.server]
    27017=127.0.0.1:27017
    
    [sslexport.client]
    8080=my.other.server:443
    
Then to run, just do this:

    sslexport sslexport.ini 
    
That's it.
