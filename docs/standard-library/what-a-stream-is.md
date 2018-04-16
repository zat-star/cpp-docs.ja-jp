---
title: "ストリームとは何か |Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- reading data [C++], iostream programming
- data [C++], reading
- streams [C++], in iostream classes
- streams [C++]
ms.assetid: a7e661e9-6cd1-4543-a9a4-c58ee9fd32f3
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 7515c587a651b31bce7f3d1c56777a2a908c488a
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/23/2018
---
# <a name="what-a-stream-is"></a>ストリームとは何か
C と同じように、C++ には組み込み入出力機能がありません。 ただし、すべての C++ コンパイラには、iostream クラスと呼ばれる、体系的でオブジェクト指向の I/O パッケージがバンドルされています。 ストリームは、iostream クラスの中心となる概念です。 ストリーム オブジェクトは、バイトのソースおよび宛先として機能するスマート ファイルと考えることができます。 ストリームの特性は、ストリームのクラスによって、およびカスタマイズされた挿入演算子と抽出演算子によって決まります。  
  
 ディスク オペレーティング システムは、デバイス ドライバーを介して、キーボード、画面、プリンター、および通信ポートを、拡張ファイルとして処理します。 iostream クラスは、これらの拡張ファイルとやり取りします。 組み込みクラスでは、ディスク I/O と同じ構文でメモリからの読み取りとメモリへの書き込みをサポートしているため、ストリーム クラスを簡単に派生させることができます。  
  
## <a name="in-this-section"></a>このセクションの内容  
 [入出力の代替手段](../standard-library/input-output-alternatives.md)  
  
## <a name="see-also"></a>参照  
 [iostream プログラミング](../standard-library/iostream-programming.md)

