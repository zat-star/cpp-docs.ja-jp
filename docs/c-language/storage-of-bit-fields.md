---
title: "ビット フィールドの格納 | Microsoft Docs"
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
ms.assetid: 4816a241-1580-4d1c-82ed-13d359733959
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
ms.openlocfilehash: 2f064c4585aa1d3c71914b1106bb056c5259d48b
ms.contentlocale: ja-jp
ms.lasthandoff: 02/24/2017

---
# <a name="storage-of-bit-fields"></a>Storage of Bit Fields (ビット フィールドの格納)
**ANSI 3.5.2.1** int 内のビット フィールドの割り当て順序  
  
 ビット フィールドは、整数内で最下位ビットから最上位ビットへと割り当てられます。 次のコードでは、  
  
```  
struct mybitfields  
{  
   unsigned a : 4;  
   unsigned b : 5;  
   unsigned c : 7;  
} test;  
  
int main( void )  
{  
   test.a = 2;  
   test.b = 31;  
   test.c = 0;  
}  
```  
  
 ビットは次のように配置されます。  
  
```  
00000001 11110010  
cccccccb bbbbaaaa  
```  
  
 80x86 プロセッサは整数値の下位バイトを上位バイトの前に格納するため、上記の整数 0x01F2 は、0xF2 の後ろに 0x01 が続くように物理メモリに格納されます。  
  
## <a name="see-also"></a>関連項目  
 [構造体、共用体、列挙体、ビット フィールド](../c-language/structures-unions-enumerations-and-bit-fields.md)
