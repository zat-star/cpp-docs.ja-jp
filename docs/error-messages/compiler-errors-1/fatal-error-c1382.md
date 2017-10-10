---
title: "致命的なエラー C1382 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C1382
dev_langs:
- C++
helpviewer_keywords:
- C1382
ms.assetid: 7a100f8c-3179-4927-a2f1-98de4c753850
caps.latest.revision: 9
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: ddb016e14b01b3bc1dfd45c7d5a8ad1aa489ac3a
ms.contentlocale: ja-jp
ms.lasthandoff: 10/10/2017

---
# <a name="fatal-error-c1382"></a>致命的なエラー C1382
PCH ファイル 'file' が、'obj' が生成されてから再構築されました。 このオブジェクトをリビルドしてください。  
  
 使用する場合[/LTCG](../../build/reference/ltcg-link-time-code-generation.md)、それを指している CIL .obj よりも新しい .pch ファイルが検出されました。 CIL .obj ファイル内の情報は期限切れです。 オブジェクトを再構築します。  
  
 コンパイルする場合にも C1382 **/Yc**に渡すことも複数のソース コード ファイル、コンパイラが、します。  解決するを使用しないで**/Yc**コンパイラに複数のソース コード ファイルを渡すときにします。  詳細については、次を参照してください。 [/Yc (プリコンパイル済みヘッダー ファイルの作成)](../../build/reference/yc-create-precompiled-header-file.md)です。
