---
title: "CMetaFileDC クラス | Microsoft Docs"
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
  - "CMetaFileDC"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CMetaFileDC クラス"
  - "メタファイル, 実装"
  - "Windows のメタファイル [C++]"
ms.assetid: ffce60fa-4181-4d46-9832-25e46fad4db4
caps.latest.revision: 23
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CMetaFileDC クラス
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

イメージやテキストを自由に作成するための一連のグラフィック デバイス インターフェイス \(GDI\) コマンドを含む Windows のメタファイルを実装します。  
  
## 構文  
  
```  
class CMetaFileDC : public CDC  
```  
  
## メンバー  
  
### パブリック コンストラクター  
  
|名前|説明|  
|--------|--------|  
|[CMetaFileDC::CMetaFileDC](../Topic/CMetaFileDC::CMetaFileDC.md)|`CMetaFileDC` オブジェクトを構築します。|  
  
### パブリック メソッド  
  
|名前|説明|  
|--------|--------|  
|[CMetaFileDC::Close](../Topic/CMetaFileDC::Close.md)|デバイス コンテキストを閉じ、メタファイルのハンドルを作成します。|  
|[CMetaFileDC::CloseEnhanced](../Topic/CMetaFileDC::CloseEnhanced.md)|拡張メタファイルのデバイス コンテキストを閉じ、拡張メタファイルのハンドルを作成します。|  
|[CMetaFileDC::Create](../Topic/CMetaFileDC::Create.md)|Windows メタファイルのデバイス コンテキストを作成し、`CMetaFileDC` のオブジェクトにアタッチします。|  
|[CMetaFileDC::CreateEnhanced](../Topic/CMetaFileDC::CreateEnhanced.md)|拡張フォーマットのメタファイルのメタファイルのデバイス コンテキストを作成します。|  
  
## 解説  
 Windows メタファイルを実行するには、最初に `CMetaFileDC` のオブジェクトを作成します。  `CMetaFileDC` のコンストラクターを起動し、Windows メタファイルのデバイス コンテキストを作成し、`CMetaFileDC` のオブジェクトに関連する [&#91;作成&#93;](../Topic/CMetaFileDC::Create.md) のメンバー関数を呼び出します。  
  
 次の転送は `CMetaFileDC` のオブジェクトのシーケンスの `CDC` GDI それに再生するようにコマンド。  出力を、`MoveTo` と `LineTo`など、作成する GDI のコマンドのみ使用できます。  
  
 メタファイルに必要なコマンドを送信した後、メタファイルのデバイス コンテキストを閉じ、メタファイルのハンドルを返します **\[閉じる\]** のメンバー関数を呼び出します。  次 `CMetaFileDC` のオブジェクトを破棄します。  
  
 [CDC::PlayMetaFile](../Topic/CDC::PlayMetaFile.md) は、メタファイルを繰り返し再生するには、メタファイルのハンドルを使用できます。  ディスクにコピーされたメタファイルをメタファイルは、[CopyMetaFile](http://msdn.microsoft.com/library/windows/desktop/dd183480)などの Windows 関数によって操作できます。  
  
 メタファイルが必要なくなった場合、[DeleteMetaFile](http://msdn.microsoft.com/library/windows/desktop/dd183537) Windows 関数のメモリから削除します。  
  
 出力された呼び出しを処理し、`GetTextExtent`のような GDI の呼び出しを属性ができるように、`CMetaFileDC` オブジェクトを実装できます。  このメタファイルは、柔軟性より簡単に頻繁に出力の組み合わせで構成され、属性が呼び出す一般的な GDI コードを再利用できます。  `CMetaFileDC` のクラスは 2 種類のデバイス コンテキスト `m_hDC`、および `CDC`から `m_hAttribDC`を継承します。  `m_hDC` のデバイス コンテキストは、すべての [CDC](../Topic/CDC%20Class.md) の GDI の出力の呼び出しと `m_hAttribDC` のデバイス コンテキストのハンドルをすべての `CDC` の GDI の属性の呼び出し処理します。  通常、これらの二つのデバイス コンテキストが同じデバイスを示します。  `CMetaFileDC`の場合、属性の DC **null** には既定でに設定されます。  
  
 画面、プリンター、またはメタファイル以外のデバイスを指す 2 番目のデバイス コンテキストを作成して、`m_hAttribDC`と新しいデバイス コンテキストを関連付けるに `SetAttribDC` のメンバー関数を呼び出します。  情報の GDI の呼び出しは、新しい `m_hAttribDC`に、指示されます。  出力は `m_hDC`GDI の呼び出しに入ります、メタファイルを表します。  
  
 `CMetaFileDC`の詳細については、[デバイス コンテキスト](../Topic/Device%20Contexts.md)を参照してください。  
  
## 継承階層  
 [CObject](../Topic/CObject%20Class.md)  
  
 [CDC](../Topic/CDC%20Class.md)  
  
 `CMetaFileDC`  
  
## 必要条件  
 **Header:** afxext.h  
  
## 参照  
 [CDC クラス](../Topic/CDC%20Class.md)   
 [階層図](../../mfc/hierarchy-chart.md)