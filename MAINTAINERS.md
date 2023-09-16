# To Create A New Release

Steps:
1. On an Amazon Linux EC2 image using the **version of node** you want. Then:
    1. `npm install muhammara` # Install muhammara
    1. `vi package.json` # Update the muhammara version
    1. `npm install`
1. Copy the muhammara.node file to this repo
    1. `cp node_modules/muhammara/binding/muhammara.node binding/muhammara.node`
1. Zip it up
    1. `cd binding/`
    1. `rm muhammara.node.zip` # Remove the old one, if it exists
    1. `zip muhammara.node.zip muhammara.node`
1. Delete the unzipped version
    1. `rm muhammara.node`
1. Update package.json with the new version info
1. Publish it
    1. `npm publish`
1. Commit and push your changes
1. Create [a new release on GitHub](https://github.com/CherryCircle/lambda-muhammara/releases/new)
