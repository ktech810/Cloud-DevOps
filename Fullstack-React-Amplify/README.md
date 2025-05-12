This project will be focused around deploying and hosting a simple React App and observing any auto-changes from Amplify whenever any code changes are made.

---
First I created a simple React application using the command:

<b>npm create vite@latest notesapp -- --template react</b>


![ViteReactTerminal](https://github.com/user-attachments/assets/2230c624-f4ca-4bc9-9cbd-940178d3911b)

<p></p>


![ViteReactBrowser](https://github.com/user-attachments/assets/84bd75dc-75ae-4b9d-a0a8-4bc3ebf40e8c)

<p></p>

I created a repository in Git then added all my code and artifacts

![ReactRepoKtech](https://github.com/user-attachments/assets/0d080bd3-2acc-49f5-b2ff-dd9761085ef8)

I then signed into my AWS account and connected my recently created Github Repo to AWS Amplify. Doing so enables me to build, deploy and host my app on AWS.

![AmplifySelectGit](https://github.com/user-attachments/assets/c3402ca0-db41-4999-9ba4-3a3fc7f62afc)

![DeployedReactApp](https://github.com/user-attachments/assets/e8ad90b5-4e75-4235-8506-6e79e10badf8)

And after waiting a few minutes, I'm able to access the URL given from Amplify that directly points to the URL that hosts my React app from the beginning.

![ReactAppURLAmp](https://github.com/user-attachments/assets/35f5878d-bc5a-4eaa-a212-4047fcd31ac5)

And when I make any code changes locally on my app ("Hello from Amplify"), I see that Amplify automatically updates those changes and reflects them. Really cool!

<img width="515" alt="UpdatedCode" src="https://github.com/user-attachments/assets/84b72668-cf66-4282-85b5-62db826d955b" />

![AmpDeployingafterCodeUpdatre](https://github.com/user-attachments/assets/fec72ae0-cf0b-48a9-88b5-1163c731f122)

![Screenshot 2025-05-12 at 4 16 15 PM](https://github.com/user-attachments/assets/6e37221d-7873-4490-94c0-2a63bb66ee25)



