This is a list of non-trivial problems I have come across in the front-end community over the past few years. It mostly exists as a personal reminder. [Let me know](https://twitter.com/PhilippSpiess) if you have something that should be added here!


- **Bundle coverage:** A lot of the code that is shipped in today’s bundles (CSS, JS, etc.) is not needed for the first render.
- **Data waterfalls:** Waterfalls is a term used to describe serial loading dependencies. E.g. to render a list of users we first download the list component, wait for it to load, then the list component makes a request to an API, waits for it to load, etc. 
  
  This is the number one issue that I have seen causing websites to be slow. It often manifests itself as a myriad of uncontrolled loading states that sometimes end in another loading state popping up. 😵‍💫
  
  An interresting observation: Most applications could be able to resolve all the data needed for the initial page load on the server side based on the URL, params, and authentication tokens.
- **Overfetching/underfetching:** A client should only ever get as many data as it needs to render. Anything more is not needed and everything less is not enough.
- **Interaction delays**: If I interact with an item on the website, it should show an instant response. 
- **Layout shifts:** Once the first elements on a website are shown, you don't want to have them jump around. This only causes confusion to the user and results in a poor experience.
- **Efficiency:** This is a meta-term for a few lower-level optimzations that rarely cause problems (but when they do, they are noticable):
	- Memory usage
	- Heavy CPU usage
	- Uncontrollede scheduled tasks (e.g. `setInterval`)
	- Browser rendering issues
	- Network/IO overhead
- **Developer experience**
	- I think this term is often overused but the current way we write apps is definitely not the end game. We need constant 
- **Hydration**
	- When you have a server-rendered HTML page and it needs to become interactive ASAP.