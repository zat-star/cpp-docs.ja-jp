---
title: "static ストレージ クラス指定子 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- static variables, specifier
- storage classes, static
- static storage class specifiers
ms.assetid: 9bce361e-919b-46b9-8148-40d7ab0eb024
caps.latest.revision: "7"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: c957b78eeb506e9f1f91a670cf5cc4d52ad72878
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="static-storage-class-specifier"></a>static ストレージ クラス指定子
**static** のストレージ クラス指定子により内部レベルで宣言された変数には、グローバル有効期間がありますが、宣言されたブロック内でのみ表示されます。 定数文字列の場合、**static** を使用すると、頻繁に呼び出される関数で頻度の高い初期化のオーバーヘッドを軽減するのに役立ちます。  
  
## <a name="remarks"></a>コメント  
明示的に**静的**変数を初期化しない場合、既定で 0 に初期化されます。 関数内で、**static** はストレージを割り当てますが、定義として動作します。 内部静的変数は、1 つの関数にのみプライベートの永続ストレージ変数を提供します。  
  
## <a name="see-also"></a>参照  
[C ストレージ クラス](c-storage-classes.md)  
[ストレージ クラス (C++)](../cpp/storage-classes-cpp.md)  