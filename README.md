# CBNetworking


[![Gitter](https://badges.gitter.im/Join Chat.svg)](https://gitter.im/cbangchen/CBNetworking#) [![MIT Licence](https://badges.frapsoft.com/os/mit/mit.svg?v=102)](https://opensource.org/licenses/mit-license.php) [![Open Source Love](https://badges.frapsoft.com/os/v2/open-source.svg?v=102)](https://github.com/ellerbrock/open-source-badge/)    

A second Encapsulation of AFNetworking!!

## Installation with CocoaPods

CocoaPods is a dependency manager for Objective-C

### Podfile

```
source 'https://github.com/CocoaPods/Specs.git'
platform :ios, '7.0'

pod 'CBNetworking', '~> 1.0.2'
```

Then, **cd** you directory and  run the following command:

```
$ pod install
```
## Architecture

### CBNetworkStatus
- CBNetworkStatusUnknown
- CBNetworkStatusNotReachable
- CBNetworkStatusNormal

### CBRequestType
- CBPOSTRequest
- CBGETRequest

### CBSerializerType
- CBHTTPSerializer
- CBJSONSerializer

---

## Basic Usage

### Creating a Request Task

```
+ (CBURLSessionTask *)requestWithUrl:(NSString *)url
                              params:(NSDictionary *)params
                         httpMedthod:(CBRequestType)httpMethod
                               cache:(BOOL)cache
                       progressBlock:(CBDownloadProgress)progressBlock
                        successBlock:(CBResponseSuccessBlock)successBlock
                           failBlock:(CBResponseFailBlock)failBlock;
```
### Creating an Image Upload Task

```
+ (CBURLSessionTask *)uploadWithImage:(UIImage *)image
                                  url:(NSString *)url
                                name:(NSString *)name
                                type:(NSString *)type
                              params:(NSDictionary *)params
                       progressBlock:(CBUploadProgressBlock)progressBlock
                        successBlock:(CBResponseSuccessBlock)successBlock
                           failBlock:(CBResponseFailBlock)failBlock;
```
### Creating an File Upload Task

```
+ (CBURLSessionTask *)uploadFileWithUrl:(NSString *)url
                          uploadingFile:(NSString *)uploadingFile
                          progressBlock:(CBUploadProgressBlock)progressBlock
                           successBlock:(CBResponseSuccessBlock)successBlock
                              failBlock:(CBResponseFailBlock)failBlock;
```

### Creating an File Download Task

```
+ (CBURLSessionTask *)downloadWithUrl:(NSString *)url
                           saveToPath:(NSString *)saveToPath
                        progressBlock:(CBDownloadProgress)progressBlock
                         successBlock:(CBResponseSuccessBlock)successBlock
                            failBlock:(CBResponseFailBlock)failBlock;

```

## Task Manager

### Cancel All Request

```
+ (void)cancelAllRequest;
```

### Cancel Request With Url

```
+ (void)cancelRequestWithURL:(NSString *)url;
```

## Cache Manager

### Get Total Cache Size

```
+ (unsigned long long)totalCacheSize;
```

### Clear Cache 

```
+ (void)clearCaches;
```

## License
CBNetworking is released under the MIT license. See LICENSE for details.






