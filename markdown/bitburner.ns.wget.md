<!-- Do not edit this file. It is automatically generated by API Documenter. -->

[Home](./index.md) &gt; [bitburner](./bitburner.md) &gt; [NS](./bitburner.ns.md) &gt; [wget](./bitburner.ns.wget.md)

## NS.wget() method

Download a file from the internet.

<b>Signature:</b>

```typescript
wget(url: string, target: string, host?: string): Promise<boolean>;
```

## Parameters

|  Parameter | Type | Description |
|  --- | --- | --- |
|  url | string | URL to pull data from. |
|  target | string | Filename to write data to. Must be script or text file. |
|  host | string | Optional hostname/ip of server for target file. |

<b>Returns:</b>

Promise&lt;boolean&gt;

True if the data was successfully retrieved from the URL, false otherwise.

## Remarks

RAM cost: 0 GB

Retrieves data from a URL and downloads it to a file on the specified server. The data can only be downloaded to a script (.script, .ns, .js) or a text file (.txt). If the file already exists, it will be overwritten by this command. Note that it will not be possible to download data from many websites because they do not allow cross-origin resource sharing (CORS).

IMPORTANT: This is an asynchronous function that returns a Promise. The Promise’s resolved value will be a boolean indicating whether or not the data was successfully retrieved from the URL. Because the function is async and returns a Promise, it is recommended you use wget in NetscriptJS (Netscript 2.0).

In NetscriptJS, you must preface any call to wget with the await keyword (like you would hack or sleep). wget will still work in Netscript 1.0, but the functions execution will not be synchronous (i.e. it may not execute when you expect/want it to). Furthermore, since Promises are not supported in ES5, you will not be able to process the returned value of wget in Netscript 1.0.

## Example


```ts
wget("https://raw.githubusercontent.com/danielyxie/bitburner/master/README.md", "game_readme.txt");
```

