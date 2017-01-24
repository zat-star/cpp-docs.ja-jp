---
title: "CDumpContext クラス | Microsoft Docs"
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
  - "CDumpContext"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "AfxDump オブジェクト"
  - "CDumpContext クラス"
  - "診断, 診断クラス"
  - "診断クラス"
  - "診断, 診断クラス"
ms.assetid: 98c52b2d-14b5-48ed-b423-479a4d1c60fa
caps.latest.revision: 20
caps.handback.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CDumpContext クラス
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

人が読み取ることができる形式でテキストを出力するために、ストリームに依存した診断出力をサポートします。  
  
## 構文  
  
```  
class CDumpContext  
```  
  
## メンバー  
  
### パブリック コンストラクター  
  
|名前|説明|  
|--------|--------|  
|[CDumpContext::CDumpContext](../Topic/CDumpContext::CDumpContext.md)|`CDumpContext` オブジェクトを構築します。|  
  
### パブリック メソッド  
  
|名前|説明|  
|--------|--------|  
|[CDumpContext::DumpAsHex](../Topic/CDumpContext::DumpAsHex.md)|16 進数形式で名前付きの項目をダンプします。|  
|[CDumpContext::Flush](../Topic/CDumpContext::Flush.md)|ダンプ コンテキスト バッファーのデータをフラッシュします。|  
|[CDumpContext::GetDepth](../Topic/CDumpContext::GetDepth.md)|ダンプの深さに対応する整数を取得します。|  
|[CDumpContext::HexDump](../Topic/CDumpContext::HexDump.md)|16 進数形式の配列に含まれるダンプのバイト数。|  
|[CDumpContext::SetDepth](../Topic/CDumpContext::SetDepth.md)|ダンプの深さを設定します。|  
  
### パブリック演算子  
  
|名前|説明|  
|--------|--------|  
|[CDumpContext::operator \<\<](../Topic/CDumpContext::operator%20%3C%3C.md)|ダンプ コンテキストに挿入の変数とオブジェクト。|  
  
## 解説  
 `CDumpContext` には、基本クラスはありません。  
  
 アプリケーションのダンプ、ほとんどの場合 [afxDump](../Topic/afxDump%20\(CDumpContext%20in%20MFC\).md)の `CDumpContext` の predeclared オブジェクトを使用することもできます。  `afxDump` のオブジェクトは、Microsoft Foundation Class ライブラリのデバッグ バージョンでだけ使用できます。  
  
 出力のメモリの [診断サービス](../Topic/Diagnostic%20Services.md) の複数の使用 `afxDump`。  
  
 ウィンドウ環境では、`cerr` ストリームと Windows 関数 **OutputDebugString**によってデバッガーに、概念的によく似た `afxDump` の定義済みオブジェクトからの出力にルーティングされます。  
  
 `CDumpContext` のクラスにオブジェクト データをダンプ `CObject` ポインターのオーバーロードされた挿入 \(**\<\<**\) 演算子があります。  派生オブジェクトのカスタム ダンプ形式が必要な場合は、[CObject::Dump](../Topic/CObject::Dump.md)をオーバーライドします。  ほとんどの Microsoft Foundation では実装をオーバーライド `Dump` のメンバー関数並べ替えます。  
  
 **CFileStatus**、`CPoint`と `CRect`など、頻繁に使用される構造がように、`CObject`から、`CString`など、`CTime`と `CTimeSpan`派生クラスに、独自の `CDumpContext` のオーバーロードされた挿入演算子があります。  
  
 クラスの実装で [IMPLEMENT\_DYNAMIC](../Topic/IMPLEMENT_DYNAMIC.md) をまたは [IMPLEMENT\_SERIAL](../Topic/IMPLEMENT_SERIAL.md) のマクロを使用すると、`CObject::Dump` は、の派生クラス `CObject`の名前を出力します。  それ以外の場合は `CObject`を出力します。  
  
 `CDumpContext` のクラスは、ライブラリのデバッグ バージョンとリリース バージョンの両方で使用できますが、`Dump` のメンバー関数はデバッグ バージョンでのみ定義します。  カスタム `Dump` のメンバー関数を含む、診断コードを、かっこにするに **\#ifdef \_DEBUG** \/ `#endif` のステートメントを使用します。  
  
 `CDumpContext` に独自のオブジェクトを作成する前に、ダンプのコピー先として使用 `CFile` のオブジェクトを作成する必要があります。  
  
 `CDumpContext`の詳細については、[MFC アプリケーションのデバッグ](../Topic/MFC%20Debugging%20Techniques.md)を参照してください。  
  
 **\#define の\_DEBUG**  
  
## 継承階層  
 `CDumpContext`  
  
## 必要条件  
 **ヘッダー:** afx.h  
  
## 参照  
 [階層図](../../mfc/hierarchy-chart.md)   
 [CFile クラス](../../mfc/reference/cfile-class.md)   
 [CObject クラス](../Topic/CObject%20Class.md)