---
title: "不完全な型 | Microsoft Docs"
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
helpviewer_keywords:
- void keyword [C], incomplete
- types [C], incomplete
- incomplete types
- unions, incomplete
- arrays [C], incomplete types
- void keyword [C]
- structures, incomplete
ms.assetid: 01bc0cf6-9fa7-458c-9371-ecbe54ea6aee
caps.latest.revision: 6
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Human Translation
ms.sourcegitcommit: a937c9d083a7e4331af63323a19fb207142604a0
ms.openlocfilehash: 89de19cb4a6fceca93a2ca3ec8ced10aaaf2c31f
ms.contentlocale: ja-jp
ms.lasthandoff: 02/24/2017

---
# <a name="incomplete-types"></a>不完全な型
不完全な型とは、識別子を記述する型でありながら、識別子のサイズを決定するために必要な情報が欠けている型です。 "不完全な型" には次のようなものがあります。  
  
-   メンバーがまだ指定されていない構造体型。  
  
-   メンバーがまだ指定されていない共用体型。  
  
-   次元がまだ指定されていない配列型。  
  
 void 型は、完全にすることのできない不完全な型です。 不完全な型を完全にするには、欠けている情報を指定します。 次の例では、不完全な型を作成する方法と完全にする方法について説明します。  
  
-   不完全な構造体型を作成するには、メンバーを指定しないで構造体型を宣言します。 この例では、`ps` ポインターは `student` という不完全な構造体型を指しています。  
  
    ```  
    struct student *ps;  
    ```  
  
-   不完全な構造体型を完全にするには、後で同じスコープ内で、メンバーを指定して同じ構造体型を宣言します。  
  
    ```  
    struct student  
    {  
        int num;  
    }                   /* student structure now completed */  
    ```  
  
-   不完全な配列型を作成するには、繰り返し回数を指定しないで配列型を宣言します。 例:  
  
    ```  
    char a[];  /* a has incomplete type */  
    ```  
  
-   不完全な配列型を完全にするには、後で同じスコープ内で、繰り返し回数を指定して同じ名前を宣言します。  
  
    ```  
    char a[25]; /* a now has complete type */  
    ```  
  
## <a name="see-also"></a>関連項目  
 [宣言と型](../c-language/declarations-and-types.md)
