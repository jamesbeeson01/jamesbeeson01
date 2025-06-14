# James Beeson 🐝

Hello there! 👋

I am a data science student passionate about improving education, and using my research and data science skills to get there. I am also a lucky husband and proud father of a precious daughter.

- 🍎 I’m currently working on AI in Education research
- 🏫 I am a senior at Brigham Young University - Idaho
- 💻 I work in the BYUI faculty technology center, a place of technology innovation to help teachers and learners on campus

Languages:
- R (tidyverse)
- Python (pandas, OOP, ArcGIS)
- AutoLISP (AutoCAD Map 3D automation)

## Blog

### Web Dev is New: Building an AI Chat Bot Using AI
**6/14/2025**

I have a deep focus right now on questions of AI in education. What are some ways AI chat use can harm learning? What bounds should be placed on AI to mitigate these risks? How are students currently using AI to augment their education? What systems can we put in place to make an AI chat bot more supportive of quality, lasting learning. I decided I would answer these questions in 3 ways: 

1. Review academic literature and reading material on AI and the theory of learning.
2. View people's candid learning conversations with AI.
3. Try to influence learning by creating my own AI chat and assessing its efficacy (including human testing). 

In diving into the literature, I realized the learning curve I would face, having to mix qualitative and quantitative research while defining abstract ideas like "learning" or what good learning means. So far, I have learned that young adults and teenagers especially are starting to see themselves handing too much of their problem solving and decision making to AI, which has been coined as cognitive offloading. I have also seen a theme of needing to gain AI competencies. We need to understand what AI actually is if we want to use it well and keep it within its bounds. I will write more on those ideas later. For now, as I started to hit roadblocks, I decided to work on all three steps of the process at the same time. Now, I have reached a major milestone in the software development for stage 3.

In the age of vibe-coding, I thought I could not only use Gemini APIs to customize a chat but also pull together a website to use it, and I did! You can find the site here:
https://www.tutor-chat.space/

It is a chat bot used primarily for research, with its use disclaimers, survey, and the whole research gambit. Most importantly, it will allow me fine control around how the chat operates and allow me to view conversations linked to surveys to view a person's experience holistically. Right now, it just calls a standard version of Gemini, but it will do some very interesting things in the near future.

The biggest milestone and achievement for me is creating a website when I didn't know web dev. Now I know slightly more.

I went into creating this website with the following knowledge:
- The general structure of html and css
- html is structure, while css is design format
- I needed a backend, and
- I have used javascript lightly

While I used some YouTube tutorials (especially to learn what node.js was and how http communications work), the heavy lifting both for the website programming and teaching me about web development came from AI. It was able to give me specific answers to questions that get into the nitty gritty. I was able to ask questions as I saw how it coded, and was able to critize its code that helped me learn the important concepts.

In the process of vibe-coding website, I learned the following about the website programming and how frontend communicates with backend:
- javascript runs natively in the browser, which is its original purpose
- node.js is a runtime for javascript that lets it run outside a browser
- express is a useful library for simplifying a web app
- The difference between get and post requests is that post gives information before receiving
- How to fetch api calls (including my own server's apis), which use JSON and urls to communicate 
- Asynchronous functions are different than static functions in that they can be called at any time in any order
- JSON was modeled after javascript objects, but they are in fact different (I learned what a javascript object was)
- I still need frontend javascript even if I have backend javascript
- The frontend is handled by each person's computer, whereas the backend is one instance that serves everyone

I also found a learning curve in the process of publishing the website, which felt incredibly more complex than I expected. In the deployment process, I learned:
- I can't just click a button to deploy
- There are multiple ways to deploy a website
- Some methods try to put as much as possible into the frontend to minimize lag and backend usage
- Some websites opt for calling functions as a service instead of a traditional backend server
- Often databases are stored externally from the hosting service
- Some hosting offerings are stateless only
- Stateless means that the information from the session goes away on session end
- I need to get a separate domain name that routes to the ip address for my website
- In opting for a cloud virtual machine, I have to install git, node, and various other packages fresh
- I also have to get an SSL certificate for security (and the golden https status)
- How to store environment variables locally and in the VM

And I am sure there are more. I did not even touch on using the Gemini API, which I have yet to dive deeply into. I was amazed at how much agent mode with Claude was able to do for me. I started by simply saying something like "give me a basic express node web app that mimics an AI chat like ChatGPT." Out of the gate it created a nice shell that I could iterate with. I found that learning beforehand what node.js was and the principles of how websites communicate, it was much easier to critize when the AI was doing something stupid and I could correct it. Having other programming background also helped me have a language to communicate with the AI and let it know what I want changed. AI was invaluable when it came to publishing the website because it had enough complexities and custom scenarios that are hard to navigate with typical tutorials. I was able to get advice on which method to use for my hosting needs, and it helped me identify any holes in my knowledge that were stopping me from getting it published.

Here is that link again: 
https://www.tutor-chat.space/

Right now, it is a relief to have something that people can see and touch (metaphorically). There is more to do, though. 

Back to the research! And playing with Gemini...
