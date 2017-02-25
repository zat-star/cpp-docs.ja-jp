---
title: "CSecurityAttributes クラス | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "ATL.CSecurityAttributes"
  - "ATL::CSecurityAttributes"
  - "CSecurityAttributes"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CSecurityAttributes クラス"
ms.assetid: a094880c-52e1-4a28-97ff-752d5869908e
caps.latest.revision: 24
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 27
---
# CSecurityAttributes クラス
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

このクラスは、セキュリティ属性の構造の Thin ラッパーです。  
  
> [!IMPORTANT]
>  このクラスおよびメンバーは、Windows のランタイムで実行するアプリケーションで使用することはできません。  
  
## 構文  
  
```  
  
class CSecurityAttributes : public SECURITY_ATTRIBUTES  
  
```  
  
## メンバー  
  
### パブリック コンストラクター  
  
|名前|説明|  
|--------|--------|  
|[CSecurityAttributes::CSecurityAttributes](../Topic/CSecurityAttributes::CSecurityAttributes.md)|コンストラクターです。|  
  
### パブリック メソッド  
  
|名前|説明|  
|--------|--------|  
|[CSecurityAttributes::Set](../Topic/CSecurityAttributes::Set.md)|`CSecurityAttributes` のオブジェクトの属性を設定するには、このメソッドを呼び出します。|  
  
## 解説  
 **SECURITY\_ATTRIBUTES** の構造はこの構造体の指定によって取得されたハンドルが継承できることをオブジェクトの作成に使用する [セキュリティ記述子](http://msdn.microsoft.com/library/windows/desktop/aa379561) を含むかどうかを指定します。  
  
 Windows のアクセスの制御モデルの概要については、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]の [アクセス制御](http://msdn.microsoft.com/library/windows/desktop/aa374860) を参照してください。  
  
## 継承階層  
 `SECURITY_ATTRIBUTES`  
  
 `CSecurityAttributes`  
  
## 必要条件  
 **ヘッダー :** atlsecurity.h  
  
## 参照  
 [セキュリティのサンプル](../../top/visual-cpp-samples.md)   
 [SECURITY\_ATTRIBUTES](http://msdn.microsoft.com/library/windows/desktop/aa379560)   
 [security descriptor](http://msdn.microsoft.com/library/windows/desktop/aa379561)   
 [クラスの概要](../../atl/atl-class-overview.md)   
 [セキュリティに関するグローバル関数](../../atl/reference/security-global-functions.md)