---
date: 2024-03-07
---

The VS Code extension runtime uses Node.js (via Electron) and you can thus use Node.js related debugging tool. 

Here's a quick guide on how to record performances traces of VS Code extensions:

   ```bash
   /Applications/Visual\ Studio\ Code/Contents/MacOS/Electron --inspect-extensions=9333
   ```
1. After VS Code is started, you want to head over to Chrome and go to `about://tracing` which should open up a view like this:  

   ![](https://gist.github.com/assets/458591/0a17881b-5449-48d5-a53e-5556f4f2dedd)
1. From here you want to configre the inspect server that we just started on port 9333. To do this, click on "Open dedicated DevTools for Node", go to the "Connection" tab if that is not open yet, and make sure to add `localhost:9333` to the list like this:

   ![](https://gist.github.com/assets/458591/972ce113-88f0-482a-99b7-5e51957981ef)
1. Now, head back to the `about://tracing` tab and you should see a new remote target that you can inspect. For me this looks like this:

   ![](https://gist.github.com/assets/458591/06b2e293-aea7-42e8-a9cc-592863b6fb07)
1. Clicking this will open a (somewhat reduced) DevTools view. Great! We've almost got it. From here you can go to the "Performance" tab to record a trace. Then, swap tabs to the VS Code window and interact with the extension. Come back later to stop the recording and export it. Voila!
   ![](https://gist.github.com/assets/458591/d590636b-31e5-4436-8039-ee62b7a8e59f)


