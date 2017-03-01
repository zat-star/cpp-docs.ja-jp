---
title: "リソース コンパイラの致命的なエラー RC1015 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- RC1015
dev_langs:
- C++
helpviewer_keywords:
- RC1015
ms.assetid: 23f187e1-5538-40b5-9042-edd2888f55c2
caps.latest.revision: 6
author: corob-msft
ms.author: corob
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
translationtype: Machine Translation
ms.sourcegitcommit: 3168772cbb7e8127523bc2fc2da5cc9b4f59beb8
ms.openlocfilehash: c466abac9b74c2f33f81f4b2ba771ffaf728ad94
ms.lasthandoff: 02/24/2017

---
# <a name="resource-compiler-fatal-error-rc1015"></a>リソース コンパイラの致命的なエラー RC1015
インクルード ファイル 'filename' を開くことはできません。  
  
 指定したインクルード ファイルが存在しないかを開けませんでしたが見つかりませんでした。  
  
 環境設定が有効であることと、ファイルの正しいパスを指定していることを確認してください。 十分なファイル ハンドルが、リソース コンパイラで使用できることを確認します。 ファイルがネットワーク ドライブ上にある場合は、ファイルを開く権限があることを確認します。  
  
 [全般] プロパティ ページ->-> リソース構成のプロパティで追加のインクルード ディレクトリとして指定されたディレクトリにインクルード ファイルが存在する場合でも、RC1015 が発生することができます。インクルード ファイルへの完全パスを指定します。  
  
 詳細については、サポート技術情報記事 Q326987 を参照してください: RC1015 エラー時に使用する場合にリソース ビュー インクルード パスが長すぎます。
