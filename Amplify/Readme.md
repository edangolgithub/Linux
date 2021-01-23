
```
npm install -g @aws-amplify/cli
amplify configure
npm install --save aws-amplify @aws-amplify/ui-react
```
## to use
```
import Amplify from 'aws-amplify';
import awsconfig from './aws-exports';
import { AmplifySignOut, withAuthenticator } from '@aws-amplify/ui-react';

Amplify.configure(awsconfig);
```
