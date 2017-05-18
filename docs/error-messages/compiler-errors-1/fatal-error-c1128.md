---
title: "致命的なエラー C1128 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C1128
dev_langs:
- C++
helpviewer_keywords:
- C1128
ms.assetid: 6f9580fd-ecef-48be-9780-dcf666704279
caps.latest.revision: 11
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Machine Translation
ms.sourcegitcommit: 3168772cbb7e8127523bc2fc2da5cc9b4f59beb8
ms.openlocfilehash: 7c70243c6fe3acf50e46c6bdf0880ed713b4b16c
ms.contentlocale: ja-jp
ms.lasthandoff: 02/24/2017

---
# <a name="fatal-error-c1128"></a>致命的なエラー C1128
セクションの数がオブジェクト ファイル形式の制限を超えています : /bigobj と共にコンパイルしてください  
  
 .obj ファイルが、許容されるセクション数である COFF オブジェクト ファイル形式制限を超えました。  
  
 このセクション制限に到達できるを使用するため[/Gy](../../build/reference/gy-enable-function-level-linking.md)とデバッグ ビルドです。**/Gy**により、関数は、独自の COMDAT セクションに入ります。 デバッグ ビルドには、各 COMDAT 関数のデバッグ情報セクションがあります。  
  
 C1128 エラーは、インライン関数が多すぎることが原因で発生することもあります。  
  
 このエラーを解決するには、ソース ファイルを複数のソース コード ファイルに分割、なしでコンパイル**/Gy**を使用してコンパイル[/bigobj (セクション数を増やすので。Obj ファイル)](../../build/reference/bigobj-increase-number-of-sections-in-dot-obj-file.md)します。  せずにコンパイルする場合は、 **/Gy**、最適化処理を個別に指定する必要がありますので**/O2**と**/O1**両方を示すもので**/Gy**します。  
  
 可能であれば、デバッグ情報なしでコンパイルしてください。  
  
 また、テンプレートの固有のインスタンス化をコンパイラで出力するのではなく、別のソース コード ファイルにこれらを指定する必要もあります。  
  
 コードを移植するときに c1128 が最初に、x64 を使用する場合、コンパイラとかなり後に、x86 コンパイラです。 x64 は少なくとも 4 つのセクションではコンパイルされた各関数に関連付けられている必要が**/Gy**テンプレートまたはクラス インラインからインライン化: コード、pdata、およびヒント、および場合によっては xdata をデバッグします。  X86 は pdata を持ちません。
