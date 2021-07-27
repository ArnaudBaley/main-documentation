---
title: "Nock (Mock API calls)"
date: 2021-05-18T15:55:39+02:00
draft: false
---

**Mock API call :**

```Javascript
const nock = require("nock");

nock("http://api.service:8080")
  .defaultReplyHeaders({
    'access-control-allow-origin': '*',
    'access-control-allow-credentials': 'true'
  })
  .get("/api/contrat/signature/matching")
  .reply(200, {
    license: {
      key: "mit",
      name: "MIT License",
      spdx_id: "MIT",
      url: "https://api.github.com/licenses/mit",
      node_id: "MDc6TGljZW5zZTEz",
    },
  });
```


**Mock Express middleware (Response) :**

```JavaScript
const mockResponse = () => {
    const res = {};
    res.status = jest.fn().mockReturnValue(res);
    res.json = jest.fn().mockReturnValue(res);
    res.send = jest.fn().mockReturnValue(res);
    return res;
};
const res = mockResponse();

const test = await creation.sendMailDocuments(sendMailBody, res);

// utiliser .send ou .json en fonction de la fonction.
expect(res.json).toBeCalledWith({
    "errorDetail": "L'envoie de mail avec les documents a échoué"
});
expect(res.status).toBeCalledWith(500);
```