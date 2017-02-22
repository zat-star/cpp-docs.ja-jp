---
title: "CDacl クラス | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "ATL::CDacl"
  - "CDacl"
  - "ATL.CDacl"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CDacl クラス"
ms.assetid: 2dc76616-6362-4967-b6cf-e2d39ca37ddd
caps.latest.revision: 23
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 26
---
# CDacl クラス
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

このクラスは、随意アクセス制御リスト \(DACL: Discretionary Access\-control List\) 構造体のラッパー クラスです。  
  
> [!IMPORTANT]
>  このクラスおよびメンバーは、Windows のランタイムで実行するアプリケーションで使用することはできません。  
  
## 構文  
  
```  
  
class CDacl : public CAcl  
  
```  
  
## メンバー  
  
### パブリック コンストラクター  
  
|名前|説明|  
|--------|--------|  
|[CDacl::CDacl](../Topic/CDacl::CDacl.md)|コンストラクターです。|  
|[CDacl::~CDacl](../Topic/CDacl::~CDacl.md)|デストラクターです。|  
  
### パブリック メソッド  
  
|名前|説明|  
|--------|--------|  
|[CDacl::AddAllowedAce](../Topic/CDacl::AddAllowedAce.md)|`CDacl` のオブジェクトに許可されるアクセス制御エントリ \(ACE\) を追加します。|  
|[CDacl::AddDeniedAce](../Topic/CDacl::AddDeniedAce.md)|`CDacl` のオブジェクトが拒否された ACE を追加します。|  
|[CDacl::GetAceCount](../Topic/CDacl::GetAceCount.md)|`CDacl` のオブジェクトのアクセス制御エントリ \(ACE\) の数を返します。|  
|[CDacl::RemoveAce](../Topic/CDacl::RemoveAce.md)|`CDacl` のオブジェクトから特定のアクセス制御エントリ \(ACE\) を削除します。|  
|[CDacl::RemoveAllAces](../Topic/CDacl::RemoveAllAces.md)|`CDacl` のオブジェクトに含まれる ACE をすべて削除します。|  
  
### パブリック演算子  
  
|名前|説明|  
|--------|--------|  
|[CDacl::operator \=](../Topic/CDacl::operator%20=.md)|代入演算子。|  
  
## 解説  
 オブジェクトのセキュリティ記述子は DACL を含めることができます。  DACL はオブジェクトにアクセスできるユーザーとグループを識別する、含まれています。また、より多くのアクセス制御エントリ \(ACE\)。  DACL が空の場合 \(つまり、ゼロ ACE を含む\) の場合、明示的にアクセスは許可されないため、アクセスが暗黙的に拒否されます。  ただし、オブジェクトのセキュリティ記述子に DACL が存在しない場合、オブジェクトに無防備であり、それらすべてがに完全なアクセスがあります。  
  
 オブジェクトの DACL を取得するには、オブジェクトの所有者でオブジェクトへの READ\_CONTROL のアクセスできる必要があります。  オブジェクトの DACL を変更するには、オブジェクトに対する WRITE\_DAC アクセス許可が必要です。  
  
 `CDacl` オブジェクトの配列を作成し、追加、削除、および削除するために提供されるクラスのメソッドを使用します。  [AtlGetDacl](../Topic/AtlGetDacl.md) と [AtlSetDacl](../Topic/AtlSetDacl.md)を参照してください。  
  
 Windows のアクセスの制御モデルの概要については、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]の [アクセス制御](http://msdn.microsoft.com/library/windows/desktop/aa374860) を参照してください。  
  
## 継承階層  
 [CAcl](../../atl/reference/cacl-class.md)  
  
 `CDacl`  
  
## 必要条件  
 **ヘッダー :** atlsecurity.h  
  
## 参照  
 [セキュリティのサンプル](../../top/visual-cpp-samples.md)   
 [CAcl クラス](../../atl/reference/cacl-class.md)   
 [ACLs](http://msdn.microsoft.com/library/windows/desktop/aa374872)   
 [ACEs](http://msdn.microsoft.com/library/windows/desktop/aa374868)   
 [クラスの概要](../../atl/atl-class-overview.md)   
 [セキュリティに関するグローバル関数](../../atl/reference/security-global-functions.md)