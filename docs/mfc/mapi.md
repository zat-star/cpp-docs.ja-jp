---
title: "MAPI | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "電子メール, 有効化"
  - "有効化 (メールに対してアプリケーションを)"
  - "有効化 (MAPI に対してアプリケーションを)"
  - "メール, 有効化 (作成したアプリケーションを)"
  - "MAPI サポート (MFC で)"
  - "MAPI, MFC"
  - "メッセージング, クライアント アプリケーション"
ms.assetid: 193449f7-b131-4ab0-9301-8d4f6cd1e7c4
caps.latest.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# MAPI
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

ここでは、メッセージのクライアント アプリケーション開発者の Microsoft の MAPI \(MAPI\) について説明します。  クラス **CDocument** の MAPI のサブセットに対する MFC のサポートを提供します。ただし、全体の API をカプセル化します。  詳細については、「[MFC の MAPI サポート](../mfc/mapi-support-in-mfc.md)」を参照してください。  
  
 MAPI がメール メッセージの作成、操作、転送し、保存するメール対応アプリケーション メール使用可能になった一連の関数です。  これは、アプリケーション開発者がメール メッセージの目的とコンテンツを定義するためのツールを提供し、それらに保存されたメール メッセージの管理を柔軟に指定できます。  MAPI は、基になるメッセージング システムのメール可能にし、メールに対応するアプリケーションに依存しないアプリケーションの作成に使用できる共通インターフェイスを提供します。  
  
 メッセージング クライアントは、Microsoft Windows のメッセージング システム \(WMS\) と対話するためにヒューマン インターフェイスを提供します。  この操作は、通常、メッセージ ストレージやアドレス帳などの MAPI 準拠のプロバイダーからサービスを要求することを示します。  
  
 MAPI に関する詳細については [!INCLUDE[winSDK](../atl/includes/winsdk_md.md)]の Win32 メッセージング ガイドで、技術情報 \(MAPI\) 参照します。  
  
## このセクションの内容  
 [MFC の MAPI サポート](../mfc/mapi-support-in-mfc.md)  
  
## 参照  
 [CDocument::OnFileSendMail](../Topic/CDocument::OnFileSendMail.md)   
 [CDocument::OnUpdateFileSendMail](../Topic/CDocument::OnUpdateFileSendMail.md)   
 [COleDocument::OnFileSendMail](../Topic/COleDocument::OnFileSendMail.md)