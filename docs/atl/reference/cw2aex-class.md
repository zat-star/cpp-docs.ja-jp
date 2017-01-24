---
title: "CW2AEX クラス | Microsoft Docs"
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
  - "ATL::CW2AEX<t_nBufferLength>"
  - "CW2AEX"
  - "ATL.CW2AEX<t_nBufferLength>"
  - "ATL::CW2AEX"
  - "ATL.CW2AEX"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CW2AEX クラス"
ms.assetid: 44dc2cf5-dd30-440b-a9b9-b21b43f49843
caps.latest.revision: 21
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CW2AEX クラス
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

このクラスは、文字列変換マクロ `CT2AEX`、`CW2TEX`、`CW2CTEX`、`CT2CAEX`、および typedef **CW2A** で使用されます。  
  
> [!IMPORTANT]
>  このクラスおよびメンバーは、Windows のランタイムで実行するアプリケーションで使用することはできません。  
  
## 構文  
  
```  
  
      template<  
int t_nBufferLength= 128  
>  
class CW2AEX  
```  
  
#### パラメーター  
 `t_nBufferLength`  
 変換プロセスで使用されるバッファーのサイズ。  既定の長さは 128 バイトです。  
  
## メンバー  
  
### パブリック コンストラクター  
  
|名前|説明|  
|--------|--------|  
|[CW2AEX::CW2AEX](../Topic/CW2AEX::CW2AEX.md)|コンストラクターです。|  
|[CW2AEX::~CW2AEX](../Topic/CW2AEX::~CW2AEX.md)|デストラクターです。|  
  
### パブリック演算子  
  
|名前|説明|  
|--------|--------|  
|[CW2AEX::operator LPSTR](../Topic/CW2AEX::operator%20LPSTR.md)|変換演算子。|  
  
### パブリック データ メンバー  
  
|名前|説明|  
|--------|--------|  
|[CW2AEX::m\_psz](../Topic/CW2AEX::m_psz.md)|元の文字列を格納するデータ メンバー。|  
|[CW2AEX::m\_szBuffer](../Topic/CW2AEX::m_szBuffer.md)|変換された文字列の格納に使用される静的バッファー。|  
  
## 解説  
 追加機能は、使用 `CT2AEX`、コードの `CW2TEX`、`CW2CTEX`、`CT2CAEX`、または **CW2A** 必要ではありません。  
  
 このクラスは、変換の結果を格納するために使用される静的な固定サイズ バッファーが含まれます。  結果が静的バッファーに収まらない場合、クラスは、メモリを解放する `malloc`を使用してオブジェクトがスコープ外に出るとメモリを割り当てます。  これは、ATL の以前のバージョンで使用可能なテキスト変換マクロとは異なり、このクラスからループで使用しても安全であること、およびスタック オーバーフローしないようにします。  
  
 クラスがヒープ メモリを割り当てると、失敗すると **E\_OUTOFMEMORY**の引数で呼び出す `AtlThrow`。  
  
 既定では、ATL 変換クラスとマクロは、変換の現在のスレッドの ANSI コード ページを使用します。  特定の変換の動作をオーバーライドするには、クラスのコンストラクターに対する 2 番目のパラメーターとしてコード ページを指定します。  
  
 次のマクロは、このクラスに基づいています:  
  
-   `CT2AEX`  
  
-   `CW2TEX`  
  
-   `CW2CTEX`  
  
-   `CT2CAEX`  
  
 次の typedef は、このクラスに基づいています:  
  
-   **CW2A**  
  
 これらのテキスト変換マクロの詳細については、[ATL と MFC の文字列変換マクロ](../Topic/ATL%20and%20MFC%20String%20Conversion%20Macros.md)を参照してください。  
  
## 使用例  
 これらの文字列変換マクロの使用例については [ATL と MFC の文字列変換マクロ](../Topic/ATL%20and%20MFC%20String%20Conversion%20Macros.md) を参照してください。  
  
## 必要条件  
 **Header:** atlconv.h  
  
## 参照  
 [CA2AEX クラス](../../atl/reference/ca2aex-class.md)   
 [CA2CAEX クラス](../../atl/reference/ca2caex-class.md)   
 [CA2WEX クラス](../../atl/reference/ca2wex-class.md)   
 [CW2CWEX クラス](../../atl/reference/cw2cwex-class.md)   
 [CW2WEX クラス](../../atl/reference/cw2wex-class.md)   
 [クラスの概要](../../atl/atl-class-overview.md)