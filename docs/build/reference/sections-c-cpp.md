---
title: "セクション (C/C++) |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- SECTIONS
dev_langs:
- C++
helpviewer_keywords:
- SECTIONS .def file statement
ms.assetid: 7b974366-9ef5-4e57-bbcc-73a1df6f8857
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 0ab2f021a53e8ae685891863500feb3873e13e2e
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="sections-cc"></a>SECTIONS (C/C++)
1 つまたは複数のセクションを導入`definitions`のセクションで、プロジェクトの出力ファイルのアクセス指定子であります。  
  
```  
SECTIONS  
definitions  
```  
  
## <a name="remarks"></a>コメント  
 各定義は個別の行に指定する必要があります。 `SECTIONS`キーワードは、最初の定義と同じ行または前の行を指定できます。 .Def ファイルは、1 つまたは複数を含めることができます`SECTIONS`ステートメントです。  
  
 これは、`SECTIONS`ステートメントは、イメージ ファイルのセクションでは 1 つまたは複数の属性を設定し、セクションの各種類の既定の属性をオーバーライドするために使用できます。  
  
 形式`definitions`は。  
  
 `.section_name specifier`  
  
 ここで`.section_name`プログラム イメージ内のセクションの名前を指定し、`specifier`は次のアクセス修飾子を 1 つ以上。  
  
|修飾子|説明|  
|--------------|-----------------|  
|`EXECUTE`|セクションが実行可能ファイル|  
|`READ`|データの読み取り操作します。|  
|`SHARED`|イメージを読み込むすべてのプロセス間でセクションを共有します|  
|`WRITE`|データの書き込み操作します。|  
  
 指定子名をスペースで区切ります。 例:  
  
```  
SECTIONS  
.rdata READ WRITE  
```  
  
 `SECTIONS`セクションの一覧の先頭をマーク`definitions`です。 各`definition`別々 の行にある必要があります。 `SECTIONS`キーワードは、最初と同じ行に配置できます`definition`または前の行。 .Def ファイルは、1 つまたは複数を含めることができます`SECTIONS`ステートメントです。 `SEGMENTS`のシノニムとしてキーワードがサポートされている`SECTIONS`です。  
  
 古いバージョンの Visual C がサポートされています。  
  
```  
section [CLASS 'classname'] specifier  
```  
  
 `CLASS`キーワードは、互換性のためサポートされますは無視されます。  
  
 セクションの属性を指定するのと同じ方法は、 [/section](../../build/reference/section-specify-section-attributes.md)オプション。  
  
## <a name="see-also"></a>参照  
 [モジュール定義ステートメントに関する規則](../../build/reference/rules-for-module-definition-statements.md)