---
title: "リソース コンパイラの致命的なエラー RC1015 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: RC1015
dev_langs: C++
helpviewer_keywords: RC1015
ms.assetid: 23f187e1-5538-40b5-9042-edd2888f55c2
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 666221cf5c3e812cd856271ea97cf4966383ec20
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="resource-compiler-fatal-error-rc1015"></a>リソース コンパイラの致命的なエラー RC1015
インクルード ファイル 'filename' を開くことはできません。  
  
 指定したインクルード ファイルが存在しませんを開けませんでした、またはが見つかりませんでした。  
  
 環境設定が有効であることと、ファイルの正しいパスを指定していることを確認してください。 十分なファイル ハンドルが、リソース コンパイラで使用できることを確認します。 ネットワーク ドライブにファイルがある場合は、ファイルを開く権限があることを確認します。  
  
 -> リソースの構成のプロパティで追加のインクルード ディレクトリとして指定されたディレクトリにインクルード ファイルが存在する場合でも、RC1015 が発生する可能性が -> [全般] プロパティ ページインクルード ファイルを完全なパスを指定します。  
  
 詳細については、サポート技術情報の記事 Q326987 を参照してください: RC1015 エラーときに使用する場合にリソース ビュー インクルード パスが長すぎます。