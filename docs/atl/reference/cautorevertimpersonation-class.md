---
title: "CAutoRevertImpersonation クラス | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "ATL::CAutoRevertImpersonation"
  - "CAutoRevertImpersonation"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CAutoRevertImpersonation クラス"
ms.assetid: 43732849-1940-4bd4-9d52-7a5698bb8838
caps.latest.revision: 22
caps.handback.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CAutoRevertImpersonation クラス
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

このクラスは、スコープ外に出ると nonimpersonating 状態への [CAccessToken](../Topic/CAccessToken%20Class.md) のオブジェクトを元に戻します。  
  
## 構文  
  
```  
  
class CAutoRevertImpersonation  
  
```  
  
## メンバー  
  
### パブリック コンストラクター  
  
|名前|説明|  
|--------|--------|  
|[CAutoRevertImpersonation::CAutoRevertImpersonation](../Topic/CAutoRevertImpersonation::CAutoRevertImpersonation.md)|オブジェクトを構築します `CAutoRevertImpersonation`|  
|[CAutoRevertImpersonation::~CAutoRevertImpersonation](../Topic/CAutoRevertImpersonation::~CAutoRevertImpersonation.md)|オブジェクトを破棄し、アクセス トークンの偽装を元に戻します。|  
  
### パブリック メソッド  
  
|名前|説明|  
|--------|--------|  
|[CAutoRevertImpersonation::Attach](../Topic/CAutoRevertImpersonation::Attach.md)|アクセス トークンの偽装操作を自動化します。|  
|[CAutoRevertImpersonation::Detach](../Topic/CAutoRevertImpersonation::Detach.md)|自動偽装の操作をキャンセルします。|  
|[CAutoRevertImpersonation::GetAccessToken](../Topic/CAutoRevertImpersonation::GetAccessToken.md)|このオブジェクトに関連付けられたアクセス トークンの現在のを取得します。|  
  
## 解説  
 [アクセス トークン](http://msdn.microsoft.com/library/windows/desktop/aa374909) は、プロセスまたはスレッドのセキュリティ コンテキストを記述する場合は、Windows NT または Windows 2000 システムに記録される各ユーザー オブジェクトに割り当てられます。  これらのトークンはアクセス `CAccessToken` のクラスを表すことができます。  
  
 アクセス トークンを偽装することが必要です。  このクラスは便利として提供されますが、アクセス トークンの偽装が実行されない; これは nonimpersonated 状態にのみ自動操作を実行します。  これは、アクセス トークンの偽装がさまざまな方法で実行できるためです。  
  
 Windows のアクセスの制御モデルの概要については、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]の [アクセス制御](http://msdn.microsoft.com/library/windows/desktop/aa374860) を参照してください。  
  
## 必要条件  
 **ヘッダー :** atlsecurity.h  
  
## 参照  
 [ATLSecurity サンプル](../../top/visual-cpp-samples.md)   
 [Access Tokens](http://msdn.microsoft.com/library/windows/desktop/aa374909)   
 [クラスの概要](../../atl/atl-class-overview.md)