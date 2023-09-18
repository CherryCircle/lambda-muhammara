# To Create A New Release

Steps:
1. Start an EC2 instance and install the **version of node** that you want. For Node 16 we used `ami-033b95fb8079dc481`.
   1. `curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.39.5/install.sh | bash`
   2. `source ~/.nvm/nvm.sh`
   3. `nvm install v16` # or whatever version you want
   4. `node -v` # make sure you have the right node version
   1. `yum install git -y && yum install vi -y`
   1. `git clone https://github.com/QbDVision-Inc/lambda-muhammara.git`
   1. `cd lambda-muhammara/`
   1. `vi package.json` # Update the muhammara version
   1. `npm install` # Installs muhammara
   1. `cp node_modules/muhammara/binding/muhammara.node /tmp`
1. Back at yet another terminal on your local machine, copy the binary created back to your machine
    1. `scp ctemp:/tmp/muhammara.node binding/muhammara.node`
1. Zip it up
    1. `cd binding/`
    1. `rm muhammara.node.zip` # Remove the old one, if it exists
    1. `zip muhammara.node.zip muhammara.node`
       1. or if on Windows using 7zip: `7z a muhammara.node.zip muhammara.node`
1. Delete the unzipped version
    1. `rm muhammara.node`
1. Update package.json with the new version info
1. Publish it
    1. `npm publish`
1. Update the README.md versions, if necessary
1. Commit and push your changes
1. Create [a new release on GitHub](https://github.com/CherryCircle/lambda-muhammara/releases/new)
