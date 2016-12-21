---
title: "CA2AEX クラス | Microsoft Docs"
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
  - "ATL::CA2AEX<t_nBufferLength>"
  - "CA2AEX"
  - "ATL.CA2AEX<t_nBufferLength>"
  - "ATLCONV/CA2AEX"
  - "ATL.CA2AEX"
  - "ATL::CA2AEX"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CA2AEX クラス"
ms.assetid: 57dc65df-d9cf-4a84-99d3-6e031dde3664
caps.latest.revision: 20
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CA2AEX クラス
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

このクラスは、文字列変換マクロ `CA2TEX` と `CT2AEX`、および typedef **CA2A** で使用されます。  
  
> [!IMPORTANT]
>  このクラスおよびメンバーは、Windows のランタイムで実行するアプリケーションで使用することはできません。  
  
## 構文  
  
```  
  
      template<  
int t_nBufferLength= 128  
>  
class CA2AEX  
```  
  
#### パラメーター  
 `t_nBufferLength`  
 変換プロセスで使用されるバッファーのサイズ。  既定の長さは 128 バイトです。  
  
## メンバー  
  
### パブリック コンストラクター  
  
|名前|説明|  
|--------|--------|  
|[CA2AEX::CA2AEX](../Topic/CA2AEX::CA2AEX.md)|コンストラクターです。|  
|[CA2AEX::~CA2AEX](../Topic/CA2AEX::~CA2AEX.md)|デストラクターです。|  
  
### パブリック演算子  
  
|名前|説明|  
|--------|--------|  
|[CA2AEX::operator LPSTR](../Topic/CA2AEX::operator%20LPSTR.md)|変換演算子。|  
  
### パブリック データ メンバー  
  
|名前|説明|  
|--------|--------|  
|[CA2AEX::m\_psz](../Topic/CA2AEX::m_psz.md)|元の文字列を格納するデータ メンバー。|  
|[CA2AEX::m\_szBuffer](../Topic/CA2AEX::m_szBuffer.md)|変換された文字列の格納に使用される静的バッファー。|  
  
## 解説  
 追加機能は、使用 `CA2TEX`、独自のコードの `CT2AEX`、または **CA2A** 必要ではありません。  
  
 このクラスは、変換の結果を格納するために使用される静的な固定サイズ バッファーが含まれます。  結果が静的バッファーに収まらない場合、クラスは、メモリを解放する `malloc`を使用してオブジェクトがスコープ外に出るとメモリを割り当てます。  これは、ATL の以前のバージョンで使用可能なテキスト変換マクロとは異なり、このクラスからループで使用しても安全であること、およびスタック オーバーフローしないようにします。  
  
 クラスがヒープ メモリを割り当てると、失敗すると **E\_OUTOFMEMORY**の引数で呼び出す `AtlThrow`。  
  
 既定では、ATL 変換クラスとマクロは、変換の現在のスレッドの ANSI コード ページを使用します。  
  
 次のマクロは、このクラスに基づいています:  
  
-   `CA2TEX`  
  
-   `CT2AEX`  
  
 次の typedef は、このクラスに基づいています:  
  
-   **CA2A**  
  
 これらのテキスト変換マクロの詳細については、[ATL と MFC の文字列変換マクロ](../Topic/ATL%20and%20MFC%20String%20Conversion%20Macros.md)を参照してください。  
  
## 使用例  
 これらの文字列変換マクロの使用例については [ATL と MFC の文字列変換マクロ](../Topic/ATL%20and%20MFC%20String%20Conversion%20Macros.md) を参照してください。  
  
## 必要条件  
 **Header:** atlconv.h  
  
## 参照  
 [CA2CAEX クラス](../../atl/reference/ca2caex-class.md)   
 [CA2WEX クラス](../../atl/reference/ca2wex-class.md)   
 [CW2AEX クラス](../../atl/reference/cw2aex-class.md)   
 [CW2CWEX クラス](../../atl/reference/cw2cwex-class.md)   
 [CW2WEX クラス](../../atl/reference/cw2wex-class.md)   
 [クラスの概要](../../atl/atl-class-overview.md)