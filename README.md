# Marlette Orbs [![CircleCI](https://circleci.com/gh/MarletteFunding/marlette-orbs.svg?style=svg&circle-token=e8283ebbe6141bc6b4b8df20c0b4c0f39427e542)]

#### How do I Publish?
> Merge to master and automatically publish a new production version of your Orb!
>
> *NOTE* currently _all_ 'major' changes as defined by the Orbs-Tool Orb require manual publishing. All minor and patch changes will be automatically published.
>
>*NOTE*  In order to publish you must be a github admin and run the following command 
>`circleci orb publish promote src/@orb.yml major`

#### What happens when I push a commit?

>The Orb CI/CD pipeline begins! Your Orb will go through the `lint-pack_validate_publish-dev` workflow. The code will first be linted, then passed to the "pack" job which will take your multiple partial yaml files and condense them into a single Orb.yml file, lastly, if specified within the `config.yml`, and defined integration tests will also be ran.
>
>Based on the branch you push to, the workflow will automatically create a development version of your orb for any branch except for "Master" which will create a production release which will be automatically incremented.

#### How do I use a dev version of an orb?
>Find the version you wish to use from the circle workflow and update the version in the following line  
>`marlette-orbs: marlette-funding/marlette-orbs@dev:{{version}}`
>
>*NOTE*  Dev version will only last 90 days

#### Other helpful circleci commands
> `circleci orb validate src/@orb.yml` will make sure that the config file is valid
