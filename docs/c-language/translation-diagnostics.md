---
title: "翻訳: 診断 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
ms.assetid: 3730ca7c-0147-452d-bd4a-6a1e97e9793e
caps.latest.revision: 6
author: mikeblome
ms.author: mblome
manager: ghogen
ms.translationtype: Human Translation
ms.sourcegitcommit: d6eb43b2e77b11f4c85f6cf7e563fe743d2a7093
ms.openlocfilehash: 525f8c235a4c2500b09ac37a050d4b57fadc8fb9
ms.contentlocale: ja-jp
ms.lasthandoff: 05/18/2017

---
# <a name="translation-diagnostics"></a>変換: 診断
**ANSI 2.1.1.3** 診断を識別する方法  
  
 Microsoft C は、次の形式のエラー メッセージを生成します。  
  
```  
  
filename( line-number ) : diagnostic Cnumbermessage  
```  
  
 ここで、*filename* はエラーが発生したソース ファイルの名前、*line-number* はコンパイラがエラーを検出した行番号、`diagnostic` は "error" または "warning"、`number` は (構文に示すように先頭に **C** が付いた) 一意の 4 桁の番号、`message` は説明メッセージです。  
  
## <a name="see-also"></a>関連項目  
 [実装で定義された動作](../c-language/implementation-defined-behavior.md)
