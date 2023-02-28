# API Security

-   API (Application communication interface) is a connection between computers or between computer programs.

## Top API Security concerns

1. Broken Object Level Authorization

-   Look at how API resources are structured (ID, names)
-   Make calls to other IDS and names with your own token
-   Response differences (Response Code, time to respond, length of response)

2. Broken User Authentication

-   Bruteforce credentials
-   Password Spraying
-   Base64 "protections"
-   low entropy tokens
-   JWT weakness( no signature, captured jwt, blank password)

3. Excessive Data Exposure

-   look for Api that provide 'extra' information
-   look for interesting responses (profile, linked user, comment section, internal meta-data)
-

4. lack of Resource and Rate Limiting

-   Add thousand items , ask for list
-   DOS
-   modify requests
-

5. Broken Function Level Authorization

-   focus on APIs with multiple roles/groups
-   try undocumented HTTP methods (PATCH, PUT, POST, DELETE)
-   create items with one group/role
-   Brute /guess potential backplane operations
-   experiment with headers, request data to access admin functions.

6. Mass Assignment

-   Look for request that appear to make partial data
-   look at request and response differences
-   error messages or required field
-   combine with broken function level Auth to change data for other users
-   fuzzing

7. Security Misconfiguration

-   Check the basics (Tls Config, info leaks via headers, default credentials)
-   verbose errors
-   misconfigured framework settings
-   intermediate devices
-   call 'internal' functions with origin headers e.g. X-Remote-Addr
-

8.  Injection

-   Place Injection strings into (Tokens/API keys, Headers, Query data, Data in request body)
-   Recon/Discovery
-   2nd order injections
-

9. Improper Asset Management

-   Misconfiguration issues
-   Internal APIs are publicly accessible
-   API documentation is inaccurate
-   "Hidden"/undocumented APIs
-   Legacy APIs not decommissioned
-

10. Insufficient Logging and Monitoring

-   change guesses to decisions with data

## API Testing types

1. Blackbox - An attacker as zero knowledge
2. WhiteBox - Test with full Knowledge and scope
3. GreyBox - Like Blackbox but with limited info
4. Crystalbox - Full knowledge including source code.

## Parts of an API

An API consists of 3 parts:

1. Hostname
2. Path
3. Method

## API Recon

-   Public Information sources
-   Google dorks (intitle:inurl: ext)
-   DNS
-   Shodan
-   Github issues
-   Check developers of the API github information
-   robots.txt
-   kiterunner
-   Proxy (Burp)
-   Check if a mobile application for the API is available.
-   API documentation
-   specification file (Swagger, openAPI,)
