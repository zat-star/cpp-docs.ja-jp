---
title: 致命的なエラー C1382 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-tools
ms.tgt_pltfrm: ''
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
ms.workload:
- cplusplus
ms.openlocfilehash: 923cc957dd136147a6c749f5ebf9508ca7e2052d
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="fatal-error-c1382"></a>致命的なエラー C1382
PCH ファイル 'file' が、'obj' が生成されてから再構築されました。 このオブジェクトをリビルドしてください。  
  
 使用する場合[/LTCG](../../build/reference/ltcg-link-time-code-generation.md)、それを指している CIL .obj よりも新しい .pch ファイルが検出されました。 CIL .obj ファイル内の情報は期限切れです。 オブジェクトを再構築します。  
  
 コンパイルする場合にも C1382 **/Yc**に渡すことも複数のソース コード ファイル、コンパイラが、します。  解決するを使用しないで**/Yc**コンパイラに複数のソース コード ファイルを渡すときにします。  詳細については、次を参照してください。 [/Yc (プリコンパイル済みヘッダー ファイルの作成)](../../build/reference/yc-create-precompiled-header-file.md)です。