---
title: "以前のオペレーティング システムにおける CImage の制限 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "CImage"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CImage クラス, 制限事項"
ms.assetid: 4bedaab8-7dd1-4c91-ab35-b75fb56765b0
caps.latest.revision: 10
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 以前のオペレーティング システムにおける CImage の制限
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

`CImage` の多くの関数は Windows の新しいバージョンを使用する: Windows 95 と Windows 98 または Windows NT 4.0、または Windows 2000。  ここでは、特定のメソッドのバージョンの制限事項について説明します。  
  
 [CImage::PlgBlt](../Topic/CImage::PlgBlt.md) と [CImage::MaskBlt](../Topic/CImage::MaskBlt.md) は Windows NT のみ 4.0 以降を使用してください。  そのため、Windows 95 と Windows 98 以降で動作するアプリケーションで実行されます。  
  
 これらのメソッドを使用するに msimg32.lib とリンクする必要があるため[CImage::AlphaBlend](../Topic/CImage::AlphaBlend.md) と [CImage::TransparentBlt](../Topic/CImage::TransparentBlt.md) は Windows 2000 以降では、Windows 98 以降でのみ使用します。このライブラリは、Windows 2000 以降では、Windows 98 以降を実行するアプリケーションにのみ使用できます\)。  
  
 これらのメソッドが呼び出されない場合は Windows 95 および Windows NT 4.0 で実行されるアプリケーションに `AlphaBlend` と `TransparentBlt` を含めることができます。  アプリケーションがこれらのメソッドが含まれ、以前のオペレーティング システムで実行する必要 msimg32.lib で遅延読み込みを実行するには、リンカーの [\/delayload](../build/reference/delayload-delay-load-import.md) を使用する必要があります。  Windows NT 4.0 または Windows 95 アプリケーションは、これらのメソッドのうち 1 つを呼び出さない限り、で実行中 msimg32.lib を読み込むようにわけではありません。  確認できます。透明度サポートが使用できるかどうか `CImage::IsTransparencySupported` のメソッドを使用します。  
  
## 使用例  
 [!code-cpp[NVC_MFCDocViewSDI#8](../mfc/codesnippet/CPP/cimage-limitations-with-earlier-operating-systems_1.cpp)]  
  
 これらのメソッドを呼び出すアプリケーションをコンパイルするには、Windows のバージョンと同じか、または 5.0 であることを示すシステム ヘッダーを \#including \_WIN32\_WINNT の前に \#define ステートメントを挿入する:  
  
 [!code-cpp[NVC_MFCDocViewSDI#9](../mfc/codesnippet/CPP/cimage-limitations-with-earlier-operating-systems_2.h)]  
  
 アプリケーションが Windows 2000 または Windows 98 より前のオペレーティング システムで実行する必要がある場合 msimg32.lib に **\/delayload**を使用せずに直接リンクできます。  
  
 [CImage::Draw](../Topic/CImage::Draw.md) は Windows NT 4.0 または Windows 95 とする、Windows 2000、および Windows 98 で使用した場合の動作が変わります。  
  
 値に設定された\_WIN32\_WINNT のアプリケーションを 0x0500 未満コンパイルする場合は、**描画** は機能しますが、Windows 2000 と Windows 98 を実行するシステムの透過性を後で自動的に処理しません。  
  
 0x0500 に設定されるか、より大きな\_WIN32\_WINNT でアプリケーションをコンパイルする場合 **描画** は Windows 2000 または Windows 98 を実行するシステムの透過性を後で自動的に処理します。  また、Windows NT 4.0 および Windows 95 以上の透過性をサポートしない、;動作 ただし、`AlphaBlend` と `TransparentBlt`の msimg32.LIB の読み込みを、上記のように遅延するために **\/delayload** を使用する必要があります。  
  
## 参照  
 [CImage クラス](../atl-mfc-shared/reference/cimage-class.md)