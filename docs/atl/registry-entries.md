---
title: "レジストリ エントリ | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "レジストリ, アプケーション ID"
  - "レジストリ, ATL サービス エントリ"
ms.assetid: 881989b7-61bb-459a-a13e-3bfcb33e184e
caps.latest.revision: 10
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# レジストリ エントリ
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

DCOM は、レジストリの一元的な場所に一つ以上の DCOM のオブジェクトの構成オプションをグループ化するアプリケーションの ID \(AppIDs\) の概念が導入されました。  オブジェクトの CLSID の下にという名前の AppID 値に値を指定することによって AppID を指定します。  
  
 既定では、ATL 生成されたサービスは、AppID に対して GUID として CLSID を使用します。  `HKEY_CLASSES_ROOT\AppID`の下に、DCOM 特定のエントリを指定できます。  最初に、2 エントリです:  
  
-   サービスの名前と同じ値を持つ`LocalService`。  この値がの場合、CLSID の下に `LocalServer32` キーの代わりに使用されます。  
  
-   `–Service`と同じ値を持つ`ServiceParameters`。  この値は、起動時サービスに渡すパラメーターを指定します。  なく `WinMain`に、これらのパラメーターに渡されるサービスの `ServiceMain` 関数注意してください。  
  
 DCOM、サービスも `HKEY_CLASSES_ROOT\AppID`の下の別のキーを作成する必要があります。  このキーは、AppID に戻すエントリを指す AppID の値を含むため、EXE の名前と等しく、相互参照として機能します。  
  
## 参照  
 [サービス](../atl/atl-services.md)