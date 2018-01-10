---
title: "コンパイラの警告 (レベル 4) C4121 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C4121
dev_langs: C++
helpviewer_keywords: C4121
ms.assetid: 8c5b85c9-2543-426b-88bc-319c50158c7e
caps.latest.revision: "10"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 4886f8274ed8813cf556529efe657dca786f0e36
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-4-c4121"></a>コンパイラの警告 (レベル 4) C4121
'symbol' : メンバーのアラインメントは過剰にパッキングされています  
  
 コンパイラは、パッキング境界で構造体メンバーをアラインするために埋め込みを追加しましたが、パッキング値はメンバーのサイズを下回ります。 たとえば、次のコード スニペットでは C4121 が生成されます。  
  
```  
// C4121.cpp  
// compile with: /W4 /c  
#pragma pack(2)  
struct s  
{  
   char a;  
   int b; // C4121  
   long long c;  
};  
```  
  
 この問題を解決するには、次のいずれかの変更を行います。  
  
-   パッキング サイズを、警告を発生させたメンバーのサイズまたはそれ以上の値に変更します。 たとえば、このスニペットでは、`pack(2)` を `pack(4)` または `pack(8)` に変更します。  
  
-   メンバー宣言をサイズに基づいて降順に並べ替えます。 このスニペットでは、構造体メンバーを逆の順序に並べ替えます。つまり、`long long` メンバーを `int` の前に配置し、`int` を `char` の前に配置します。  
  
 この警告は、コンパイラがデータ メンバーの前に埋め込みを追加した場合にのみ発生します。 パッキングによってデータ型用にアラインされていないメモリ位置にデータが配置されたが、データ メンバーの前に埋め込みが追加されなかったときは発生しません。 データのサイズの倍数となる境界でデータがアラインされていないと、パフォーマンスが低下する可能性があります。 アラインされていないデータの読み取りおよび書き込みにより、一部のアーキテクチャでプロセッサ障害が発生した場合は、その障害の解決に桁違いの時間がかかる場合があります。 アラインされていないデータのアクセスは、一部の RISC アーキテクチャには移植できません。  
  
 使用することができます[#pragma pack](../../preprocessor/pack.md)または[/Zp](../../build/reference/zp-struct-member-alignment.md)構造体の配置を指定します。 (コンパイラでは、この警告は生成しません**/Zp1**が指定されている)。