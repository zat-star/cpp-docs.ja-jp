---
title: "CFont クラス | Microsoft Docs"
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
  - "CFont"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CFont クラス"
  - "フォント, MFC クラス"
  - "GDI, フォント クラス"
ms.assetid: 3fad6bfe-d6ce-4ab9-967a-5ce0aa102800
caps.latest.revision: 23
caps.handback.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CFont クラス
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Windows のグラフィック デバイス インターフェイス \(GDI\) のフォントをカプセル化したもので、フォントを操作するメンバー関数を提供します。  
  
## 構文  
  
```  
class CFont : public CGdiObject  
```  
  
## メンバー  
  
### パブリック コンストラクター  
  
|名前|説明|  
|--------|--------|  
|[CFont::CFont](../Topic/CFont::CFont.md)|`CFont` オブジェクトを構築します。|  
  
### パブリック メソッド  
  
|名前|説明|  
|--------|--------|  
|[CFont::CreateFont](../Topic/CFont::CreateFont.md)|指定された特性の `CFont` を初期化します。|  
|[CFont::CreateFontIndirect](../Topic/CFont::CreateFontIndirect.md)|`LOGFONT` の構造体で指定された特性で `CFont` のオブジェクトを初期化します。|  
|[CFont::CreatePointFont](../Topic/CFont::CreatePointFont.md)|ポイントの秒単位の高さを指定 `CFont` およびタイプフェイスを初期化します。|  
|[CFont::CreatePointFontIndirect](../Topic/CFont::CreatePointFontIndirect.md)|`CreateFontIndirect` ただし、フォント高さと同様に論理単位ではなくポイントの 1\/10 で測定されます。|  
|[CFont::FromHandle](../Topic/CFont::FromHandle.md)|Windows **HFONT**が指定されている場合、`CFont` オブジェクトへのポインターを返します。|  
|[CFont::GetLogFont](../Topic/CFont::GetLogFont.md)|`CFont` のオブジェクトにアタッチされる論理フォントに関する情報で `LOGFONT` を塗りつぶします。|  
  
### パブリック演算子  
  
|名前|説明|  
|--------|--------|  
|[CFont::operator HFONT](../Topic/CFont::operator%20HFONT.md)|アタッチされた `CFont` のオブジェクトに Windows GDI フォントのハンドルを返します。|  
  
## 解説  
 `CFont` のオブジェクトを、[CreateFont](../Topic/CFont::CreateFont.md)使用するには、[CreateFontIndirect](../Topic/CFont::CreateFontIndirect.md)、[CreatePointFont](../Topic/CFont::CreatePointFont.md)、または [CreatePointFontIndirect](../Topic/CFont::CreatePointFontIndirect.md)を使用してオブジェクトへの `CFont` オブジェクトを構築し、Windows フォントをアタッチし、オブジェクトのメンバーを使用するフォントを処理します。  
  
 `CreatePointFont` と `CreatePointFontIndirect` 関数は、ポイント数の論理単位にフォントの高さの変換を自動的に動作するため `CreateFont` 使用するか `CreateFontIndirect` より簡単です。  
  
 `CFont`の詳細については、[グラフィカル オブジェクト](../../mfc/graphic-objects.md)を参照してください。  
  
## 継承階層  
 [CObject](../Topic/CObject%20Class.md)  
  
 [CGdiObject](../../mfc/reference/cgdiobject-class.md)  
  
 `CFont`  
  
## 必要条件  
 **ヘッダー:** afxwin.h  
  
## 参照  
 [MFC HIERSVR サンプル](../../top/visual-cpp-samples.md)   
 [CGdiObject クラス](../../mfc/reference/cgdiobject-class.md)   
 [階層図](../../mfc/hierarchy-chart.md)