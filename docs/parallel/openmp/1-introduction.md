---
title: "1. 概要 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
ms.assetid: c42e72bc-0e31-4b1c-b670-cd82673c0c5a
caps.latest.revision: "6"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: f850e236ebfd056da93700df06ec830e5a573284
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="1-introduction"></a>1.はじめに
このドキュメントでは、コンパイラ ディレクティブ、ライブラリ関数、および C および C++ プログラムで共有メモリの並列処理を指定するために使用する環境変数のコレクションを指定します。 このドキュメントで説明されている機能と総称、 *OpenMP C と C++ アプリケーション プログラム インターフェイス (API)*です。 この仕様の目的は、並列プログラミング モデルを提供するさまざまなベンダーから共有メモリ アーキテクチャ間で移植できるプログラムです。 OpenMP C と C++ API は、多くのベンダーからのコンパイラでサポートされます。 詳細については、OpenMP など、 *OpenMP Fortran アプリケーション プログラム インターフェイス*、次の web サイトで見つかんだことができます。  
  
 [http://www.openmp.org](http://www.openmp.org)  
  
 ディレクティブ、ライブラリ関数、およびこのドキュメントで定義されている環境変数、ユーザーが作成および移植性を確保しながら並列プログラムを管理します。 ディレクティブは、C の拡張し複数の data (SPMD) コンス トラクターの work-sharing コンス トラクター、および同期構造は、1 つのプログラムを使用するシーケンシャルの C++ プログラミング モデルし、の共有とプライベート データのサポートを提供します。 OpenMP C および C++ API をサポートするコンパイラを有効にし、すべての OpenMP コンパイラ ディレクティブの解釈は、コンパイラにコマンド ライン オプションが含まれます。