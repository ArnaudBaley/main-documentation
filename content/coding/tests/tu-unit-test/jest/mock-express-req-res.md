---
title: "Mock Express Request & Response"
date: 2021-05-18T15:55:39+02:00
draft: false
---

## Mock functions `helper.js`: 

```Javascript
const mockServerResponse = () => {
    const response = {};
    response.body = {
        message: 'All good'
    }
    response.status = 200;
    return response;
};

const mockExpressRes = () => {
    const res = {};
    res.send = jest.fn().mockReturnValue(res)
    res.status = jest.fn().mockReturnValue(res)
    res.json = jest.fn().mockReturnValue(res)
    res.sendStatus = jest.fn().mockReturnValue(res)
    return res
};

module.exports = {
    mockServerResponse,
    mockExpressRes,
};
```

## Use in test : 

```Javascript
import network from '../../../../src/server/utils/network';
import helper from '../../../Helper/back/helper';

describe('passePlat', () => {
    test('passePlat : status 200 + body response', () => {
        const response = helper.mockServerResponse();
        const res = helper.mockExpressRes();

        network.passePlat(response, res);

        expect(res.status).toHaveBeenCalledWith(200);
        expect(res.send).toHaveBeenCalledWith({"message": "All good"});
        expect(res.sendStatus).not.toHaveBeenCalled();
    });
});

```