---
title: "Platform::Metadata::RuntimeClassName | Microsoft Docs"
ms.custom: ""
ms.date: "12/30/2016"
ms.prod: "windows-client-threshold"
ms.technology: ""
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "Platform/Platform::Metadata::RuntimeClassName"
helpviewer_keywords: 
  - "RuntimeClassName"
  - "Platform::Metadata::RuntimeClassName"
ms.assetid: fdef8f85-ab94-4edd-ba50-ee0da9358ff6
caps.latest.revision: 2
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
caps.handback.revision: 2
---
# Platform::Metadata::RuntimeClassName
クラス定義に適用された場合、プライベート クラスが GetRuntimeClassName 関数から有効な名前を返すことを確認します。  
  
## 構文  
  
```vb  
[Platform::Metadata::RuntimeClassName] name  
```  
  
#### パラメーター  
 name  
  
 Windows ランタイムで表示される既存のパブリックの種類の名前です。  
  
## 解説  
 プライベート ref クラスのこの属性を使用して、カスタム ランタイムの種類の名前、および既存の名前が要件を満たさない場合を指定します。 名前としてクラスが実装するパブリック インターフェイスを指定します。  
  
## 使用例  
 この属性を使用する方法の例を次に示します。 この例では、HellowWorldImpl のランタイムの種類の名前は Test::Native::MyComponent::IHelloWorld です。  
  
```  
  
namespace Test  
{  
    namespace Native  
    {  
        namespace MyComponent  
        {  
            public interface class IHelloWorld  
            {  
                Platform::String^ SayHello();  
            };  
  
            private ref class HelloWorldImpl sealed :[Platform::Metadata::RuntimeClassName] IHelloWorld  
            {  
            public:  
                HelloWorldImpl();  
                virtual Platform::String^ SayHello();  
            };  
  
            Platform::String^ HelloWorldImpl::SayHello()  
            {  
                return L"Hello World!";  
            }  
        }  
    }  
}  
```  
  
## 参照  
 [Platform::Metadata 名前空間](../cppcx/platform-metadata-namespace.md)