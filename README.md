

# Blitz Documentation

Event Name: Blitz 1

Date: 30/09/2023


Purpose: The purpose of the Blitz Event is to crash test my URL Shortener deployment in a sense, for instance, testing my website for latency.

# What Happened During the Blitz?
## Story
<P><em>Nike emailed about the URL Shortener.In Nike's email, Nike mentioned customers are complaining about
  the amount of time it takes to load their webpages.Nike will like us to reduce the amount of latency
  customers are experiencing.</em>
</P>



## Preparation:
<ul>
  <h2>Set our Configurations for the Blitz</h2>
  <li>Select a Blitz Package</li>
  <li>Set number of threads(users) to 1000</li>
  <li>Set protocol to http</li>
  <li>Put in the URL of Url shortener application in Server name and IP address selection</li>
</ul>
<p><strong>During the blitz I noticed we did have a high latency of 40.89 ms </strong></p>
<img width="725" alt="Screenshot 2023-09-30 at 9 28 20 AM" src="https://github.com/NMonKLabs77/Blitz1/assets/139259756/436755a2-58f1-4561-92cc-c361a73cdc6d">

# Reducing the latency of URL Shortener
<p>The best method to reduce our latency to use a CDN(Content Delivery Network) whose purpose is to store static webpages or webpages that your clients use frequently.
  When the webpage is requested, the CDN serves up the static webpage in record time due to the webpage already being stored up and ready for use.In the case of AWS I used
  a service called Cloud Front which is AWS flavor of CDNs
</p>
## Steps to take to setup  of Cloud Front
<ul>
  <li>Search AWS services and navigate to Cloud Front</li>
<h2>Create our distribution</h2>
  <li>Put in our Url for Url Shortener Application</li>
  <li>Set it to HTTP only</li>
  <li>Set cache policy to CachingOptimized</li>
  <li></li>
</ul>

## Test for Latency Reduction

<ul>
  <li>Copy the new cloundfront.net URL</li>
  <h2>Set up a new configuration for Blitz using the URL of cloudfront</h2>
  <li>Put in Url for Cloud Front</li>
  <li>Set protocol to http</li>
  <li>Set rewuest method to get</li>
</ul>
<p>When I ran the Blitz the first thing I noticed was that our latency went down very low. From 40.89 ms to 9.652 ms.Mission Successful!</p>

<img width="748" alt="Screenshot 2023-09-30 at 9 53 39 AM" src="https://github.com/NMonKLabs77/Blitz1/assets/139259756/774d38fe-9da7-4f08-a057-b092dd6e87d9">



