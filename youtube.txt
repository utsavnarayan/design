YouTube design:
1.	Frontend: ReactJS
a.	V1: Progressive single-page WebApp that will act as mobile website (mobile-friendly)
b.	V2: PhoneGap or ReactNative based App 
c.	V3: Native Android and iOS Apps
2.	Middle layer: Web Service: Python + Scala
a.	Microservice 1: Manage User authentication (OAuth2/Google+/FB Logins) + Custom registration and login
b.	Micrososervice 2: Handle telemetry and usage data
i.	V1: Use Google Analytics or Microsofts’s App Insights or Adobe Omniture Analytics
ii.	V2: Capture more details using custom events and logic
c.	Microservice 3: Provide streaming videos
d.	Microservice 4: handle Image thumbnails and other image related info
e.	Other Microservices: For handling channels, subscriptions, playlists
3.	Backend: MySQL + MongoDB + Redis
a.	Host on AWS
b.	EC2 machines with Large EBS Backed SSD Volumes for storing Data
c.	AWS RDS Aurora/MySQL for storing elementary User info
d.	AWS MongoDB for storing most other data
e.	AWS Redis/Memcache for caching
f.	AWS S3 for storing all other files and images
g.	AWS Glacier for backups
4.	Machine Learning
a.	Detect Fraud of copyright infringement (Deep Learning: Google Tensor flow)
b.	Deep Learning based subtitles
c.	Use GraphDB or Machine learning for suggesting content
5.	Video Processing Layer:
a.	Use g-series EC2 instances that have graphics card for best video conversion/transcoding and saving videos in multiple resolutions
b.	Peer to peer based system for reading same video from multiple systems while serving any client

Notes:
1.	Each EBS Volume storing video should be backed-up/replicated with another EBS Volume
2.	DBs should be replicated across multiple availability zones

TODO:
1.	Expose YouTube API, Embedded Videos
2.	Setup AutoScale for WebServices
Rough notes:
1.	1 million monthly users
2.	0.5 million weekly users
3.	1 million hits everyday
4.	0.5 million videos uploaded daily average size 50 MB
5.	Recommendation engine design
