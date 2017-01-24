---
title: "CW2WEX クラス | Microsoft Docs"
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
  - "CW2WEX"
  - "ATL.CW2WEX<t_nBufferLength>"
  - "ATL::CW2WEX"
  - "ATL.CW2WEX"
  - "ATL::CW2WEX<t_nBufferLength>"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CW2WEX クラス"
ms.assetid: 46262e56-e0d2-41fe-855b-0b67ecc8fcd7
caps.latest.revision: 20
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CW2WEX クラス
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

このクラスは、文字列変換マクロ `CW2TEX` と `CT2WEX`、および typedef `CW2W` で使用されます。  
  
> [!IMPORTANT]
>  このクラスおよびメンバーは、Windows のランタイムで実行するアプリケーションで使用することはできません。  
  
## 構文  
  
```  
  
      template<  
int t_nBufferLength= 128  
>  
class CW2WEX  
```  
  
#### パラメーター  
 `t_nBufferLength`  
 変換プロセスで使用されるバッファーのサイズ。  既定の長さは 128 バイトです。  
  
## メンバー  
  
### パブリック コンストラクター  
  
|名前|説明|  
|--------|--------|  
|[CW2WEX::CW2WEX](../Topic/CW2WEX::CW2WEX.md)|コンストラクターです。|  
|[CW2WEX::~CW2WEX](../Topic/CW2WEX::~CW2WEX.md)|デストラクターです。|  
  
### パブリック演算子  
  
|名前|説明|  
|--------|--------|  
|[CW2WEX::operator LPWSTR](../Topic/CW2WEX::operator%20LPWSTR.md)|変換演算子。|  
  
### パブリック データ メンバー  
  
|名前|説明|  
|--------|--------|  
|[CW2WEX::m\_psz](../Topic/CW2WEX::m_psz.md)|元の文字列を格納するデータ メンバー。|  
|[CW2WEX::m\_szBuffer](../Topic/CW2WEX::m_szBuffer.md)|変換された文字列の格納に使用される静的バッファー。|  
  
## 解説  
 追加機能が必要ない場合は、コードで `CW2TEX`、`CT2WEX`、または `CW2W` を使用します。  
  
 このクラスは、変換の結果を格納するために使用される静的な固定サイズ バッファーが含まれます。  結果が静的バッファーに収まらない場合、クラスは、メモリを解放する `malloc`を使用してオブジェクトがスコープ外に出るとメモリを割り当てます。  これは、ATL の以前のバージョンで使用可能なテキスト変換マクロとは異なり、このクラスからループで使用しても安全であること、およびスタック オーバーフローしないようにします。  
  
 クラスがヒープ メモリを割り当てると、失敗すると **E\_OUTOFMEMORY**の引数で呼び出す `AtlThrow`。  
  
 既定では、ATL 変換クラスとマクロは、変換の現在のスレッドの ANSI コード ページを使用します。  
  
 次のマクロは、このクラスに基づいています:  
  
-   `CW2TEX`  
  
-   `CT2WEX`  
  
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
 [CW2CWEX クラス](../../atl/reference/cw2cwex-class.md)   
 [クラスの概要](../../atl/atl-class-overview.md)