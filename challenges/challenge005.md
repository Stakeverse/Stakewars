# Stake Wars Challenge 005
Published on: July 17 2020

Automatically deploy nearcore using a CI/CD pipeline.
This challenge is designed to have validators build and deploy their own node from the source code, instead of using the precompiled binaries provided by NEAR. The result is having multiple teams that can independently build and test new releases of the node, to improve the quality and security of the network as a whole.

To participate, validators will be asked to build and deploy a specific branch/tag of [nearcore](https://github.com/nearprotocol/nearcore), and keeping their nodes up to date. 

If you already run a professional validator setup, and you have CI/CD experience, you don't need any further instructions.

If you want to test yourself and use this as a learning opportunity, the list of available tools to accomplish can be very long:
- Jenkins
- Terraform
- Gitlab
- Github Actions
- Cloud provider tools (Google Cloud Build, Azure Pipelines, AWS CodePipeline...)

You may want to read [this article](https://hackernoon.com/understanding-the-basic-concepts-of-cicd-fw4k32s1) if you need some basic knowledge on CI/CD.

## Acceptance Criteria

1. Build nearcore
2. Run tests
3. Deploy the node

### 1.Build nearcore
Subscribe to the [branch beta](https://github.com/nearprotocol/nearcore/tree/beta) of nearcore, and automatically build the artifact from the source code as soon as there's a new release.

More information is available in the official documentation, in the [contribution section](https://docs.near.org/docs/contribution/nearcore) and in the [develop section](https://docs.near.org/docs/local-setup/running-testnet#compiling-and-running-official-node-without-docker)

### 2.Run tests
Once your artifact is deployed, you may want to test its networking functionality and existing applications. Some examples can be found in [nearcore scripts](https://github.com/nearprotocol/nearcore/tree/beta/scripts)

Some examples are:
- deploy multiple nodes in `localnet` mode (an example is in the [nearup repo](https://github.com/near/nearup#spawn-local-network)) and test the capacity to connect and synchronize with the network
- attach your own local services (helper, wallet, explorer)
- send transactions, deploy/call/view smart contracts
- execute load tests and measure the performance

The outcomes of these tests will help you decide if you want to deploy this release or not. NEAR will take in serious consideration the feedback of validators who setup their own suite of tests and find bugs or errors in new releases.

### 3.Deploy the node
With the merge of [nearcore PR #2701](https://github.com/nearprotocol/nearcore/pull/2701), NEAR Protocol can run different builds of the node within the same network. You can then decide which deployment stragy adopt (e.g. Blue/Green or a Canary) and merge the node keys from the previous release to the newer one.

This process may require intermediate steps, such as database migration or state resync (by deleting the `~/.near/betanet/data` folder).

## Additional considerations
In the upcoming weeks we will introduce special builds, with tags specifically for Stake Wars Challenge 005 participants. We will measure the reactivity of valdiators to newer releases, and the capacity to identify bugs or test failures prior to the node deployment.


## Contribution Opportunities

Do you want to earn extra tokens? We have contribution opportunities available below! 

Follow the Validator channel on [NEAR Portal](https://portal.near.org/topic/validator), you will find a list of available contributions to earn tokens. In order to participate, you will have to specify:
- the title of the contribution you made
- the type of document you released
- a clear reference to the available contribution below

Once your work is reviewed, you will be added to the list below. Please note that rewards in tokens will need to pass basic KYC checks from NEAR Foundation, and comply with regulations.

### List of available contributions

| Title | Abstract                    | Contributor |  Date  | Link | NEAR Tokens | Maintenance | Language |
| -------- | ------------------------------ | ----------- | ------ | ---- | ----------- | --- | ---- |
| Release a CI Pipeline doc | Create an article or a commented Github script to explain and execute an automated building and testing of a new release of nearcore. Before starting the project request approval in the NEAR portal. | - | - | - | 3,500 | 15% | - |
| Release a CD Pipeline doc | Create an article and a Github document/script to explain and execute an automated deployment of a new release of nearcore. Before starting the project request approval in the NEAR portal. | - | - | - | 3,000 | 15% | - |
| Write a localnet tutorial | Create a tutorial on how to automatically deploy and boot your own NEAR network, using it to test a new release of nearcore. | - | - | - | 1,500 | 10% | - |

## Previous Challenge
Create your warchest to dynamically keep one seat: [challenge004](challenge004.md)