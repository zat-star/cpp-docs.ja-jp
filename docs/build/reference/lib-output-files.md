---
title: "LIB の出力ファイル |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: Lib
dev_langs: C++
helpviewer_keywords: output files, LIB
ms.assetid: e73d2f9b-a42d-402b-b7e3-3a94bebb317e
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: f9796a7e6d2e91abd1fd064fb54079ea0364a828
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="lib-output-files"></a>LIB の出力ファイル
LIB によって生成された出力ファイルは、次の表に示すように、モードによって異なります。  
  
|モード|出力|  
|----------|------------|  
|既定値 (構築またはライブラリの変更)|COFF ライブラリ (.lib)|  
|/EXTRACT を持つメンバーを抽出します。|オブジェクト (.obj) ファイル|  
|ファイルの構築では、エクスポートとインポート ライブラリ/DEF の|インポート ライブラリ (.lib) とエクスポート (.exp) ファイル|  
  
## <a name="see-also"></a>参照  
 [LIB の概要](../../build/reference/overview-of-lib.md)