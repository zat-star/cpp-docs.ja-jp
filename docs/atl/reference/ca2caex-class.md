---
title: "CA2CAEX クラス | Microsoft Docs"
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
  - "ATL.CA2CAEX"
  - "ATL.CA2CAEX<t_nBufferLength>"
  - "ATLCONV/CA2CAEX"
  - "ATL::CA2CAEX<t_nBufferLength>"
  - "ATL::CA2CAEX"
  - "CA2CAEX"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CA2CAEX クラス"
ms.assetid: 388e7c1d-a144-474c-a182-b15f69a74bd8
caps.latest.revision: 20
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CA2CAEX クラス
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

このクラスは、文字列変換マクロ `CA2CTEX` と `CT2CAEX`、および typedef **CA2CA** で使用されます。  
  
> [!IMPORTANT]
>  このクラスおよびメンバーは、Windows のランタイムで実行するアプリケーションで使用することはできません。  
  
## 構文  
  
```  
  
      template<  
int t_nBufferLength= 128  
>  
class CA2CAEX  
```  
  
#### パラメーター  
 `t_nBufferLength`  
 変換プロセスで使用されるバッファーのサイズ。  既定の長さは 128 バイトです。  
  
## メンバー  
  
### パブリック コンストラクター  
  
|名前|説明|  
|--------|--------|  
|[CA2CAEX::CA2CAEX](../Topic/CA2CAEX::CA2CAEX.md)|コンストラクターです。|  
|[CA2CAEX::~CA2CAEX](../Topic/CA2CAEX::~CA2CAEX.md)|デストラクターです。|  
  
### パブリック演算子  
  
|名前|説明|  
|--------|--------|  
|[CA2CAEX::operator LPCSTR](../Topic/CA2CAEX::operator%20LPCSTR.md)|変換演算子。|  
  
### パブリック データ メンバー  
  
|名前|説明|  
|--------|--------|  
|[CA2CAEX::m\_psz](../Topic/CA2CAEX::m_psz.md)|元の文字列を格納するデータ メンバー。|  
  
## 解説  
 追加機能は、使用 `CA2CTEX`、独自のコードの `CT2CAEX`、または **CA2CA** 必要ではありません。  
  
 このクラスは、ループで使用しても安全で、スタック オーバーフローされません。  既定では、ATL 変換クラスとマクロは、変換の現在のスレッドの ANSI コード ページを使用します。  
  
 次のマクロは、このクラスに基づいています:  
  
-   `CA2CTEX`  
  
-   `CT2CAEX`  
  
 次の typedef は、このクラスに基づいています:  
  
-   **CA2CA**  
  
 これらのテキスト変換マクロの詳細については、[ATL と MFC の文字列変換マクロ](../Topic/ATL%20and%20MFC%20String%20Conversion%20Macros.md)を参照してください。  
  
## 使用例  
 これらの文字列変換マクロの使用例については [ATL と MFC の文字列変換マクロ](../Topic/ATL%20and%20MFC%20String%20Conversion%20Macros.md) を参照してください。  
  
## 必要条件  
 **Header:** atlconv.h  
  
## 参照  
 [CA2AEX クラス](../../atl/reference/ca2aex-class.md)   
 [CA2WEX クラス](../../atl/reference/ca2wex-class.md)   
 [CW2AEX クラス](../../atl/reference/cw2aex-class.md)   
 [CW2CWEX クラス](../../atl/reference/cw2cwex-class.md)   
 [CW2WEX クラス](../../atl/reference/cw2wex-class.md)   
 [クラスの概要](../../atl/atl-class-overview.md)