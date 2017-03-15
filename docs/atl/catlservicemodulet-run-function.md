---
title: "CAtlServiceModuleT::Run 関数 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "CServiceModule::Run"
  - "CServiceModule.Run"
  - "CSecurityDescriptor"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ATL サービス, セキュリティ"
ms.assetid: 42c010f0-e60e-459c-a63b-a53a24cda93b
caps.latest.revision: 12
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# CAtlServiceModuleT::Run 関数
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Run** は `PreMessageLoop`、`RunMessageLoop`と `PostMessageLoop`の呼び出しが含まれます。  を呼び出した後で、`PreMessageLoop` 1 番目のは、サービスのスレッド ID が格納されます。  サービスは、Win32 API の関数、[PostThreadMessage](http://msdn.microsoft.com/library/windows/desktop/ms644946)を使用して **WM\_QUIT** のメッセージを送信してそれ自体を閉じるには、この ID を使用します。  
  
 `PreMessageLoop` は、`InitializeSecurity`を呼び出します。  既定では、`InitializeSecurity` または無効にするセキュリティ記述子のセットに [CoInitializeSecurity](http://msdn.microsoft.com/library/windows/desktop/ms693736) を呼び出します。したがってすべてのユーザーが、オブジェクトにアクセスできることを意味します。  
  
 サービスに独自のセキュリティを指定します。オーバーライド `PreMessageLoop` は `InitializeSecurity`を呼び出さないようにし、COM は、レジストリからセキュリティ設定を行います。  レジストリ設定を構成する簡単な方法は、このセクションで後述する [DCOMCNFG](../Topic/DCOMCNFG.md) ユーティリティとあります。  
  
 セキュリティが指定されている場合、オブジェクトは COM と新しいクライアントがプログラムに接続できるように登録されます。  最後に、プログラムが実行され、プログラムがメッセージ ループに入ることは、Services Control Manager \(SCM\) を示します。  プログラムは、サービスの停止に終了られたメッセージをポストするまで実行されます。残り。  
  
## 参照  
 [サービス](../atl/atl-services.md)   
 [CSecurityDesc クラス](../atl/reference/csecuritydesc-class.md)   
 [CSid クラス](../atl/reference/csid-class.md)   
 [CDacl クラス](../atl/reference/cdacl-class.md)   
 [CAtlServiceModuleT::Run](../Topic/CAtlServiceModuleT::Run.md)