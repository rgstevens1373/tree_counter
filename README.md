Overall approach:
- Github repos for backend and front end
- Backend is a Pocketbase instance running in Render
- Front end is a static page in Render
- Use Visual Studio to edit HTML, through Github
How the tree counter works:
- Backend is in Pocketbase hosted on Render
	- Free version of Pocketbase resets and loses all configs every now and then so I had to upgrade to $7/mo plan
 	- I plan to turn off the paid Pocketbase service in January, then turn it on again in November
 - To set it up from scratch:
	- I configured a local version 
	- 	Launch Pocketbase locally
			- Github/pocketbase local
			- Open Terminal
			- ./pocketbase serve
		- Go to http://127.0.0.1:8090
		- Copy collections (app_user and tree_count) and fields
		- Set API rules for both collections to all be "1=1" (which is 'true')
		- Create one record in tree_count
		- Copy id to paste into index.html
	- Copy that id to the index.html file
		- Launch Visual Studio
		- Open rob/github/tree_counter/index.html
		- Paste in the id 
			-   const globalRecordId = "gykmuue49xdacdv"; // YOUR updated record ID
		- Save the file
		- Push to github (from Visual Studio)
Github security
- I created a "fine grained Personal Access Token with a 90 day limit
- When it expires I will need to do it again, select "content" then "read/write", apply to all repos
