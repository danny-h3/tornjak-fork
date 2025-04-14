# My Contributions to Tornjak

## Onboarding Week Tasks

- Learned Kubernetes fundamentals, including Pods, Deployments, and Services.
- Explored SPIRE (Secure Production Identity Framework for Everyone) and its role in workload identity.
- Set up a local Kubernetes cluster using Minikube/KinD for development and testing.
- Installed and configured SPIRE Server and SPIRE Agents within the Kubernetes environment.
- Got Tornjak frontend and backend working on local docker containers
- Reviewed project documentation and familiarized myself with the codebase.
- Joined project communication channels such as Slack and attended onboarding meetings with project lead Maia.
- Explored existing GitHub issues and pull requests to understand project workflows.


## Finished Issues

### Issue 585
- Link: https://github.com/spiffe/tornjak/issues/585
- Description: Created a documentation file detailing how to deploy Tornjak with helm charts
- Status: PR Under Review


## Current Issue

### Issue 584
- Link: https://github.com/spiffe/tornjak/issues/584
- Description: Frontend gets a runtime error when backend isn't running
- Status: Working on it

## Logs For Current Issue

- I've failed to reproduce the issue when running frontend in docker container (3/ 28/ 2025)
- I've successfully reproduced issue when running frontend using NPM (4/ 1/ 2025)
- Looking for possible solutions (4/ 1/ 2025)
- Analyzing which components are calling backend APIS (4/ 4/ 2025)
- Analyzed 3/16 components (4 / 6/ 2025)
- Analyzed 14/16 componenets, still can't determine what the issue is (4 / 11/ 2025)

### Component Analysis report:

```javascript
import "bootstrap/dist/css/bootstrap.min.css"; 😐
import store from 'redux/store'; 😐
import IsManager from './components/is_manager'; 😐
import { BrowserRouter as Router, Route } from "react-router-dom"; 😐
import { Provider } from 'react-redux'; 😐

// -- Components -- //

import NavigationBar from "./components/navbar"; ✅ 💾
    // -- Calls TornjakAPI
import SelectServer from "./components/select-server"; ✅ 💾
    // -- Calls TornjakAPI
import ClusterList from "./components/cluster-list"; ✅ 💾
    // -- Calls TornjakAPI
import ClusterManagement from "./components/cluster-management"; ✅ 💾
    // -- Calls TornjakAPI
import FederationList from "./components/federation-list"; ✅ 💾
    // -- Calls TornjakAPI
import TrustBundleCreate from "components/trustbundle-create"; ✅ 💾
    // -- Calls TornjakAPI
import FederationCreate from "components/federation-create"; ✅
import AgentList from "./components/agent-list"; ✅ 💾
    // -- Calls TornjakAPI
import CreateJoinToken from "./components/agent-create-join-token"; ✅
import EntryList from "./components/entry-list"; ✅ 💾
    // -- Calls TornjakAPI
import EntryCreate from "./components/entry-create"; ✅ 💾
    // -- Calls TornjakAPI
import ServerManagement from "./components/server-management"; ✅
import TornjakServerInfo from "./components/tornjak-server-info"; ✅ 💾
    // -- Calls TornjakAPI
import TornjakDashBoardStyled from "./components/dashboard/tornjak-dashboard"; ✅ 💾
    // -- Calls TornjakAPI
import DashboardDetailsRender from 'components/dashboard/dashboard-details-render'; ✅ 💾
    // -- Calls TornjakAPI
import RenderOnAdminRole from 'components/RenderOnAdminRole' ✅

import './App.css';  😐
import 'react-toastify/dist/ReactToastify.css'; 😐


✅ - Checked
⭕ - Unchecked
😐 - Useless
💾 - Contains API
```