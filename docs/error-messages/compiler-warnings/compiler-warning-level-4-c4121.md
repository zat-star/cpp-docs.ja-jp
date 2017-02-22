---
title: "Compiler Warning (level 4) C4121 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4121"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4121"
ms.assetid: 8c5b85c9-2543-426b-88bc-319c50158c7e
caps.latest.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 10
---
# Compiler Warning (level 4) C4121
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'symbol' : メンバーのアラインメントは過剰にパッキングされています  
  
 コンパイラは、パッキング境界で構造体メンバーをアラインするために埋め込みを追加しましたが、パッキング値はメンバーのサイズを下回ります。  たとえば、次のコード スニペットでは C4121 が生成されます。  
  
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
  
-   パッキング サイズを、警告を発生させたメンバーのサイズまたはそれ以上の値に変更します。  たとえば、このスニペットでは、`pack(2)` を `pack(4)` または `pack(8)` に変更します。  
  
-   メンバー宣言をサイズに基づいて降順に並べ替えます。  このスニペットでは、構造体メンバーを逆の順序に並べ替えます。つまり、`long long` メンバーを `int` の前に配置し、`int` を `char` の前に配置します。  
  
 この警告は、コンパイラがデータ メンバーの前に埋め込みを追加した場合にのみ発生します。  パッキングによってデータ型用にアラインされていないメモリ位置にデータが配置されたが、データ メンバーの前に埋め込みが追加されなかったときは発生しません。  データのサイズの倍数となる境界でデータがアラインされていないと、パフォーマンスが低下する可能性があります。  アラインされていないデータの読み取りおよび書き込みにより、一部のアーキテクチャでプロセッサ障害が発生した場合は、その障害の解決に桁違いの時間がかかる場合があります。  アラインされていないデータのアクセスは、一部の RISC アーキテクチャには移植できません。  
  
 [\#pragma pack](../../preprocessor/pack.md) または [\/Zp](../Topic/-Zp%20\(Struct%20Member%20Alignment\).md) を使用すると、構造体のアラインメントを指定できます \(**\/Zp1** が指定されている場合、この警告は生成されません\)。