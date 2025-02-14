---
layout: rsk
title: RIF Scheduler - SDK - Querying Plans
---

### Querying a plan

To schedule a transaction you need to purchase a plan. Plans are paid in tokens or RBTC.

First of all, you need to get a plan from the service provider, which will give you the price per execution, the payment token and the execution window in seconds, among other things.

```javascript
import { RifScheduler } from "@rsksmart/rif-scheduler-sdk";

const config = {
    contractAddress: serviceProviderContractAddress,
    providerOrSigner: signer
}

const rifScheduler = new RIFScheduler(config);

const planIndex = 0;
const plan = rifScheduler.getPlan(planIndex)

//  {
//    pricePerExecution: 10000000000000;
//    window: 300;
//    token: Token;
//    active: true;
//    ...
//  }
```

### Querying ALL plans

If you want to obtain all plans from the service provider, you must first get the plans count and then get the plans one by one.

```javascript
import { RifScheduler } from "@rsksmart/rif-scheduler-sdk";

const config = {
    contractAddress: serviceProviderContractAddress,
    providerOrSigner: signer
}

const rifScheduler = new RIFScheduler(config);

const plans = await rifScheduler.getPlans();

//  [{
//    pricePerExecution: 10000000000000;
//    window: 300;
//    token: Token;
//    active: true;
//    ...
//  },
//  {
//    pricePerExecution: 50000000000000;
//    window: 600;
//    token: Token;
//    active: true;
//    ...
//  }]
```

What you can do with this sdk?

- [Getting Started](../)
- [Query plans](../query-plans)
- [Purchase one of this plans](../purchasing-plan)
- [Schedule a transaction for the next minutes](../scheduling)
- [Get status](../statuses)