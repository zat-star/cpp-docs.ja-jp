---
title: "構造体の格納とアラインメント | Microsoft Docs"
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
- alignment of structures
- structure storage
- storing structures
- packing structures
ms.assetid: 60ff292f-2595-4f37-ae00-4c4b4f047196
caps.latest.revision: 8
author: mikeblome
ms.author: mblome
manager: ghogen
ms.translationtype: HT
ms.sourcegitcommit: 16d1bf59dfd4b3ef5f037aed9c0f6febfdf1a2e8
ms.openlocfilehash: d9c09137da32c7ef9d42f0302087379af922652f
ms.contentlocale: ja-jp
ms.lasthandoff: 10/09/2017

---
# <a name="storage-and-alignment-of-structures"></a>構造体の格納とアラインメント
**Microsoft 固有の仕様**  
  
 構造体メンバーは、宣言されている順に格納され、最初のメンバーが最も下位のメモリ アドレスを、最後のメンバーが最も上位のアドレスを持ちます。  
  
 すべてのデータ オブジェクトには、*alignment-requirement* (アラインメント要件) があります。 構造体の場合、要件はメンバー中で最も大きい値になります。 すべてのオブジェクトには、次の式を満たすように *offset* (オフセット) が割り当てられます。  
  
 *offset* `%` *alignment-requirement* `==` 0  
  
 隣接するビット フィールドは、同じサイズの整数型で、次のビット フィールドがビット フィールドの共通のアラインメント要件によって課される境界を越えずに現在の割り当て単位に収まる場合は、同じ 1、2、または 4 バイトの割り当て単位にパックされます。  
  
 領域を節約したり、既存のデータ構造に合わせたりするために、コンパクト化の程度を調整して構造体を格納できます。 [/Zp](../build/reference/zp-struct-member-alignment.md)[*n*] コンパイラ オプションおよび[#pragma pack](../preprocessor/pack.md)コントロールがどのようにデータを構造化が"パック"されるメモリにします。 /Zp を使用すると [*n*] オプションをどこ *n*  1、2、4、8、または 16 ですが、各構造体メンバーのアラインメント要件は、バイト境界に 1 つ目が格納された後にフィールドのパッキング サイズ (*n*)、小さい方です。 バイト境界を数式として表現すると、次のようになります。  
  
```  
min( n, sizeof( item ) )  
```  
  
 ここで *n*  /Zp で表されたパッキング サイズは、[*n*] オプションと*項目*構造体のメンバーは、します。 既定のパッキング サイズは、/Zp8 です。  
  
 `pack` プラグマを使用して、特定の構造体にコマンド ラインで指定したパッキング以外のパッキングを指定するには、構造体の前に `pack` プラグマを指定します (パッキング サイズは 1、2、4、8、または 16)。 コマンド ラインで指定したパッキングに戻すには、引数なしで `pack` プラグマを指定します。  
  
 ビット フィールドは、既定で Microsoft C コンパイラの **long** サイズに設定されます。 構造体のメンバーは、型または/Zp のサイズにアライン [*n*] サイズ、小さい方です。 既定のサイズは 4 です。  
  
 **END Microsoft 固有の仕様**  
  
## <a name="see-also"></a>関連項目  
 [構造体宣言](../c-language/structure-declarations.md)
