---
title: "予約語 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- code
- CONFORMING
- DISCARDABLE
- Description
- base
- APPLOADER
- Data
- DYNAMIC
- DEV386
dev_langs: C++
helpviewer_keywords:
- .def files [C++], reserved words
- def files [C++], reserved words
- linker [C++], reserved words
- reserved words [C++]
ms.assetid: 9b9f49e5-0739-45ab-a37e-81e3915ceb25
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 35f9a3e907b72b4b8cf8e673e771832ba3fc0527
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="reserved-words"></a>予約語
次の単語は、リンカーによって予約されています。 これらの名前を引数として使用できます[モジュール定義ステートメント](../../build/reference/module-definition-dot-def-files.md)名前が二重引用符で囲まれている場合にのみ ("") です。  
  
||||  
|-|-|-|  
|**APPLOADER**1|**INITINSTANCE**2|**プリロード**|  
|**ベース**|**に対しては IOPL**|**プライベート**|  
|**コード**|**ライブラリ**1|**PROTMODE**2|  
|**準拠しています。**|**LOADONCALL**1|**純粋な**1|  
|**データ**|****2|**読み取り専用**|  
|**説明**|**移動可能な**1|**読み取り/書き込み**|  
|**DEV386**|**MOVEABLE**1|**リアルモード**1|  
|**破棄可能**|**複数**|**常駐**|  
|**動的**|**名**|**RESIDENTNAME**1|  
|**実行専用**|**NEWFILES**2|**セクション**|  
|**EXECUTEONLY**|**NODATA**1|**セグメント**|  
|**読み取り**|**NOIOPL**1|**共有**|  
|**EXETYPE**|**NONAME**|**1 つ**|  
|**エクスポート**|**準拠していない**1|**スタックサイズ**|  
|**固定**1|**NONDISCARDABLE**|**スタブ**|  
|**関数**2|**[なし]**|**バージョン**|  
|**ヒープサイズ**|**非共有**|**WINDOWAPI**|  
|**インポート**|**NOTWINDOWCOMPAT**1|**WINDOWCOMPAT**|  
|**純粋でない**1|**オブジェクト**|**WINDOWS**|  
|**含める**2|**古い**1||  
  
 1 この用語に到達したときに、、リンカーは (「無視」)、警告を出力します。 ただし、単語は、まだ予約されています。  
  
 2、リンカーは、この単語は無視されますが、警告は出力されません。  
  
## <a name="see-also"></a>参照  
 [リンカー オプションの設定](../../build/reference/setting-linker-options.md)   
 [リンカー オプション](../../build/reference/linker-options.md)