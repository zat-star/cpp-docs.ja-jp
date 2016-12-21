---
title: "CW2CWEX クラス | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CW2CWEX"
  - "ATL::CW2CWEX"
  - "ATL.CW2CWEX"
  - "ATL.CW2CWEX<t_nBufferLength>"
  - "ATL::CW2CWEX<t_nBufferLength>"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CW2CWEX クラス"
ms.assetid: d654b22b-05a6-410f-a0ec-9a2cbbb4cca7
caps.latest.revision: 20
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CW2CWEX クラス
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

このクラスは、文字列変換マクロ `CW2CTEX` と `CT2CWEX`、および typedef `CW2W` で使用されます。  
  
> [!IMPORTANT]
>  このクラスおよびメンバーは、Windows のランタイムで実行するアプリケーションで使用することはできません。  
  
## 構文  
  
```  
  
      template<  
int t_nBufferLength= 128  
>  
class CW2CWEX  
```  
  
#### パラメーター  
 `t_nBufferLength`  
 変換プロセスで使用されるバッファーのサイズ。  既定の長さは 128 バイトです。  
  
## メンバー  
  
### パブリック コンストラクター  
  
|名前|説明|  
|--------|--------|  
|[CW2CWEX::CW2CWEX](../Topic/CW2CWEX::CW2CWEX.md)|コンストラクターです。|  
|[CW2CWEX::~CW2CWEX](../Topic/CW2CWEX::~CW2CWEX.md)|デストラクターです。|  
  
### パブリック演算子  
  
|名前|説明|  
|--------|--------|  
|[CW2CWEX::operator LPCWSTR](../Topic/CW2CWEX::operator%20LPCWSTR.md)|変換演算子。|  
  
### パブリック データ メンバー  
  
|名前|説明|  
|--------|--------|  
|[CW2CWEX::m\_psz](../Topic/CW2CWEX::m_psz.md)|元の文字列を格納するデータ メンバー。|  
  
## 解説  
 追加機能は、使用 `CW2CTEX`、コードの `CT2CWEX`、または `CW2W` 必要ではありません。  
  
 このクラスは、ループで使用しても安全で、スタック オーバーフローされません。  既定では、ATL 変換クラスとマクロは、変換の現在のスレッドの ANSI コード ページを使用します。  
  
 次のマクロは、このクラスに基づいています:  
  
-   `CW2CTEX`  
  
-   `CT2CWEX`  
  
 次の typedef は、このクラスに基づいています:  
  
-   `CW2W`  
  
 これらのテキスト変換マクロの詳細については、[ATL と MFC の文字列変換マクロ](../Topic/ATL%20and%20MFC%20String%20Conversion%20Macros.md)を参照してください。  
  
## 使用例  
 これらの文字列変換マクロの使用例については [ATL と MFC の文字列変換マクロ](../Topic/ATL%20and%20MFC%20String%20Conversion%20Macros.md) を参照してください。  
  
## 必要条件  
 **Header:** atlconv.h  
  
## 参照  
 [CA2AEX クラス](../../atl/reference/ca2aex-class.md)   
 [CA2CAEX クラス](../../atl/reference/ca2caex-class.md)   
 [CA2WEX クラス](../../atl/reference/ca2wex-class.md)   
 [CW2AEX クラス](../../atl/reference/cw2aex-class.md)   
 [CW2WEX クラス](../../atl/reference/cw2wex-class.md)   
 [クラスの概要](../../atl/atl-class-overview.md)