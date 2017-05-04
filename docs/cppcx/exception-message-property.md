---
title: "Exception::Message プロパティ | Microsoft Docs"
ms.custom: ""
ms.date: "02/09/2017"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "Platform/Platform::Exception::Message"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Exception::Message プロパティ"
ms.assetid: ad1199cd-0889-4803-ad0d-a3a7b3c51891
caps.latest.revision: 10
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# Exception::Message プロパティ
エラーを説明するメッセージです。  
  
## 構文  
  
```cpp  
public:property String^ Message;  
```  
  
## プロパティ値  
 Windows ランタイムで発生する例外では、システムで用意されているエラーの説明になります。  
  
## 解説  
 [!INCLUDE[win8](../cppcx/includes/win8-md.md)]では、このプロパティは読み取り専用です。そのバージョンの Windows ランタイムでは、例外が HRESULT として ABI のみに伝達されるためです。[!INCLUDE[win81](../cppcx/includes/win81-md.md)] では、豊富な例外情報が ABI 経由で伝達され、開発者はカスタム メッセージを提供し、他のコンポーネントにはプログラムでそのメッセージにアクセスすることができます。 詳細については、["Exceptions \(C\+\+\/CX\) \(例外 \(C\+\+\/CX\)\)"](../cppcx/exceptions-c-cx.md) を参照してください。  
  
## 必要条件  
 **サポートされている最低限のクライアント:** [!INCLUDE[win8](../cppcx/includes/win8-md.md)]  
  
 **サポートされている最低限のサーバー:** [!INCLUDE[winserver8](../cppcx/includes/winserver8-md.md)]  
  
 **名前空間:** Platform  
  
 **メタデータ:** platform.winmd  
  
## 参照  
 [Platform::Exception クラス](../cppcx/platform-exception-class.md)