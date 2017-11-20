---
title: "register ストレージ クラス指定子 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- register variables
- register storage class
ms.assetid: 7577bf48-88ec-4191-873c-ef4217a4034e
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 95c06471b7d8ea60754c29a9bde3159174e9c194
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="register-storage-class-specifier"></a>register ストレージ クラス指定子
**Microsoft 固有の仕様**  
  
 Microsoft C/C++ コンパイラは、レジスタ変数に対するユーザーの要求を考慮しません。 ただし、移植性を考慮して、**register** キーワードに関連付けられた他のセマンティクスは、すべてコンパイラによって実行されます。 たとえば、レジスタ オブジェクトに単項アドレス演算子 (**&**) を適用することはできず、配列で **register** キーワードを使用することもできません。  
  
 **END Microsoft 固有の仕様**  
  
## <a name="see-also"></a>関連項目  
 [内部レベル宣言のストレージ クラス指定子](../c-language/storage-class-specifiers-for-internal-level-declarations.md)