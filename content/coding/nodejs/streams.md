---
title: "Buffer / Streams"
date: 2021-05-18T15:55:39+02:00
draft: false
---

|  |  |  | |
| ----------- |----------- | ----------- | ----------- |
| **Stream** | Size unknown (multiple paquet called "chunk") | asynchronous | 
| **Buffer** | Size known | synchronous |

 A stream uses buffer to store chunks.

 #### Get remote file (superagent) + send it without disk persistense :
 ```JavaScript
async function downloadDocument(url, req, res) {
    let filename = req.params.idversiondocument;

    try {
        const result = await request.get(path.join(url, "/api/ged/" + req.params.idDocument + "/file"))
            .auth(req.token, {
                type: 'bearer'
            })
            .responseType('blob'); // get response as buffer (synchronous).

        res.status(result.status);
        res.write(result.body, 'binary'); // response = buffer as binary.
        return res.end();

    } catch (error) {
        logger.error(JSON.stringify(error));
        return res.status(error.status).send(error.message);
    }
};
 ```