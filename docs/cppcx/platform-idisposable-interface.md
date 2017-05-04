---
title: "Platform::IDisposable インターフェイス | Microsoft Docs"
ms.custom: ""
ms.date: "02/03/2017"
ms.prod: "windows-client-threshold"
ms.technology: ""
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "Platform/Platform::IDisposable"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Platform::IDisposable インターフェイス"
ms.assetid: f4344056-7030-42ed-bc98-b140edffddcd
caps.latest.revision: 4
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
caps.handback.revision: 2
---
# Platform::IDisposable インターフェイス
アンマネージ リソースを解放するために使用されます。  
  
## 構文  
  
```cpp  
public interface class IDisposable  
```  
  
## 属性  
 **GuidAttribute**\("de0cbaea\-8065\-4a45\-b196\-c9d443f9bab3"\)  
  
 **VersionAttribute**\(NTDDI\_WIN8\)  
  
## メンバー  
 IDisposable インターフェイスは IUnknown インターフェイスから継承します。 また IDisposable には次の種類のメンバーもあります。  
  
 **メソッド**  
  
 IDisposable インターフェイスには、次のメソッドがあります。  
  
|メソッド|説明|  
|----------|--------|  
|HYPERLINK "http:\/\/msdnpreview.redmond.corp.microsoft.com\/en\-us\/library\/windows\/apps\/platform.idisposable.dispose.aspx" Dispose|アンマネージ リソースを解放するために使用されます。|  
  
## 必要条件  
 **サポートされている最低限のクライアント:** [!INCLUDE[win8](../cppcx/includes/win8-md.md)]  
  
 **サポートされている最低限のサーバー:** [!INCLUDE[winserver8](../cppcx/includes/winserver8-md.md)]  
  
 **名前空間:** Platform