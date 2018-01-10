---
title: "&lt;codecvt&gt; 列挙型 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: codecvt/std::codecvt_mode
ms.assetid: 46a8b073-01bc-46d3-b3d3-a8540f9422c1
helpviewer_keywords: std::codecvt_mode
caps.latest.revision: "10"
manager: ghogen
ms.openlocfilehash: bba1b53abb7286c64bdaf79ec8cb2004ba67a9dd
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="ltcodecvtgt-enums"></a>&lt;codecvt&gt; 列挙型
  
##  <a name="codecvt_mode"></a>  codecvt_mode 列挙型  
 [ロケール](../standard-library/locale-class.md) ファセットの構成情報を指定します。  
  
```  
enum codecvt_mode {  
    consume_header = 4,  
    generate_header = 2,  
    little_endian = 1  
 };  
```  
  
### <a name="remarks"></a>コメント  
 列挙体では、[\<codecvt>](../standard-library/codecvt.md) で宣言されているロケール ファセットに構成情報を提供する 3 つの定数が定義されます。 それぞれの値は次のとおりです。  
  
- `consume_header`。マルチバイト シーケンスの読み取り時に初期ヘッダー シーケンスを使用し、読み取られる後続のマルチバイト シーケンスのエンディアンを決定します。  
  
- `generate_header`。マルチバイト シーケンスの書き込み時に初期ヘッダー シーケンスを生成し、書き込まれる後続のマルチバイト シーケンスのエンディアンを提供します。  
  
- `little_endian`。既定のビッグ エンディアン順ではなく、リトル エンディアン順でマルチバイト シーケンスを生成します。  
  
 これらの定数は任意の組み合わせで論理和を指定することができます。  
  
## <a name="see-also"></a>参照  
 [\<codecvt>](../standard-library/codecvt.md)

