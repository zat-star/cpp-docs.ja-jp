---
title: "範囲の読み取り | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
ms.assetid: 99de29ce-ab14-46f4-97e1-2081fd996b53
caps.latest.revision: "6"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 96748c24fbf1e5adfebb72ba809533afeafebe38
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="reading-ranges"></a>範囲の読み取り
**ANSI 4.9.6.2** `fscanf` 関数の % [ 変換でのスキャン リストの最初または最後の文字ではないダッシュ (-) 文字の解釈  
  
 次の行  
  
```  
fscanf( fileptr, "%[A-Z]", strptr);  
```  
  
 `strptr` が指す文字列に A から Z の範囲の任意の文字数を読み取ります。  
  
## <a name="see-also"></a>関連項目  
 [ライブラリ関数](../c-language/library-functions.md)