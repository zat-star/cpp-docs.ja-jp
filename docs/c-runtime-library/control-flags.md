---
title: "制御フラグ | Microsoft Docs"
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
  - "c.flags"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "デバッグ ヒープ, コントロール フラグ"
  - "フラグ, control"
  - "ヒープ割り当て, コントロール フラグ"
ms.assetid: 8dbd24a5-0633-42d1-9771-776db338465f
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 制御フラグ
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Microsoft C ランタイム ライブラリのデバッグ バージョンではヒープ割り当て、およびレポート プロセスを制御するには、次のフラグを使用します。  詳細については、「[CRT のデバッグ技術](../Topic/CRT%20Debugging%20Techniques.md)」を参照してください。  
  
|フラグ|説明|  
|---------|--------|  
|[\_CRTDBG\_MAP\_ALLOC](../c-runtime-library/crtdbg-map-alloc.md)|デバッグ バージョンのベース ヒープに対応する関数をマップします。|  
|[\_DEBUG](../Topic/_DEBUG.md)|ランタイム関数のデバッグ バージョンを使用できます。|  
|[\_crtDbgFlag](../Topic/_crtDbgFlag.md)|デバッグ ヒープ マネージャーが割り当てを追跡するコントロール|  
  
 これらのフラグはの \/D コマンド ライン オプションまたは `#define` のディレクティブで定義できます。  フラグが `#define`と定義されている場合、ディレクティブは、ヘッダー ファイルの定期的な宣言のステートメントを含む前に記述する必要があります。  
  
## 参照  
 [グローバル変数および基本データ型](../c-runtime-library/global-variables-and-standard-types.md)