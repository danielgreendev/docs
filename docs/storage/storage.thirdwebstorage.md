---
slug: /storage.thirdwebstorage
title: ThirdwebStorage class
hide_title: true
displayed_sidebar: storage
---

<!-- Do not edit this file. It is automatically generated by API Documenter. -->

# ThirdwebStorage class

Upload and download files from decentralized storage systems.

**Signature:**

```typescript
export declare class ThirdwebStorage<T extends UploadOptions = IpfsUploadBatchOptions>
```

## Example

```jsx
// Create a default storage class without any configuration
const storage = new ThirdwebStorage();

// Upload any file or JSON object
const uri = await storage.upload(data);
const result = await storage.download(uri);

// Or configure a custom uploader, downloader, and gateway URLs
const gatewayUrls = {
  // We define a mapping of schemes to gateway URLs
  "ipfs://": [
    "https://ipfs.thirdwebcdn.com/ipfs/",
    "https://cloudflare-ipfs.com/ipfs/",
    "https://ipfs.io/ipfs/",
  ],
};
const downloader = new StorageDownloader();
const uploader = new IpfsUploader();
const storage = new ThirdwebStorage({ uploader, downloader, gatewayUrls });
```

## Constructors

| Constructor                                                          | Modifiers | Description                                                         |
| -------------------------------------------------------------------- | --------- | ------------------------------------------------------------------- |
| [(constructor)(options)](./storage.thirdwebstorage._constructor_.md) |           | Constructs a new instance of the <code>ThirdwebStorage</code> class |

## Properties

| Property                                                | Modifiers | Type                                    | Description |
| ------------------------------------------------------- | --------- | --------------------------------------- | ----------- |
| [gatewayUrls](./storage.thirdwebstorage.gatewayurls.md) |           | [GatewayUrls](./storage.gatewayurls.md) |             |

## Methods

| Method                                                                 | Modifiers | Description                                                                                                                                                                        |
| ---------------------------------------------------------------------- | --------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| [download(url)](./storage.thirdwebstorage.download.md)                 |           | Downloads arbitrary data from any URL scheme.                                                                                                                                      |
| [downloadJSON(url)](./storage.thirdwebstorage.downloadjson.md)         |           | Downloads JSON data from any URL scheme. Resolves any URLs with schemes to retrievable gateway URLs.                                                                               |
| [resolveScheme(url)](./storage.thirdwebstorage.resolvescheme.md)       |           | Resolve any scheme on a URL to get a retrievable URL for the data                                                                                                                  |
| [upload(data, options)](./storage.thirdwebstorage.upload.md)           |           | Upload arbitrary file or JSON data using the configured decentralized storage system. Automatically uploads any file data within JSON objects and replaces them with hashes.       |
| [uploadBatch(data, options)](./storage.thirdwebstorage.uploadbatch.md) |           | Batch upload arbitrary file or JSON data using the configured decentralized storage system. Automatically uploads any file data within JSON objects and replaces them with hashes. |
