---
title: "方法: 特定のスケジューラ ポリシーを指定する |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- specifying scheduler policies [Concurrency Runtime]
- scheduler policies, specifying [Concurrency Runtime]
ms.assetid: 9c5149f9-ac34-4ff3-9e79-0bad103e4e6b
caps.latest.revision: "17"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 0ca5172372a9a80c419e9be54b0378f1254f4e6a
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="how-to-specify-specific-scheduler-policies"></a>方法: 特定のスケジューラ ポリシーを指定する
スケジューラでタスクを管理する場合、スケジューラ ポリシーを使用することで、スケジューラが使用する方法を制御できます。 このトピックでは、スケジューラ ポリシーを使用して、プログレス インジケーターをコンソールに出力するタスクのスレッドの優先度を高くする方法について説明します。  
  
 非同期エージェントと共にカスタム スケジューラ ポリシーを使用する例は、次を参照してください。[する方法: エージェントを使用して特定のスケジューラ ポリシーを作成する](../../parallel/concrt/how-to-create-agents-that-use-specific-scheduler-policies.md)です。  
  
## <a name="example"></a>例  
 次の例では、2 つのタスクを並列で実行します。 最初のタスクは、n を計算<sup>th</sup>フィボナッチ数。 2 番目のタスクは、プログレス インジケーターをコンソールに出力します。  
  
 最初のタスクは、再帰的な分解を使用してフィナボッチ数を計算します。 つまり、各タスクがサブタスクを再帰的に作成して全体的な結果を計算します。 再帰的な分解を使用するタスクは、利用可能なすべてのリソースを使用するため、他のタスクが処理を続行できなくなる可能性があります。 この例では、プログレス インジケーターを出力するタスクが、コンピューティング リソースに適切なタイミングでアクセスできない場合があります。  
  
 この例を出力するタスクをコンピューティング リソースに、進行状況メッセージの正当なアクセスを提供するに記載されている手順を使用して[する方法: スケジューラ インスタンスを管理](../../parallel/concrt/how-to-manage-a-scheduler-instance.md)カスタム ポリシーを持つスケジューラ インスタンスを作成します。 このカスタム ポリシーで、スレッドの優先順位が最も高い優先順位クラスとなるように指定します。  
  
 この例では、 [concurrency::call](../../parallel/concrt/reference/call-class.md)と[concurrency::timer](../../parallel/concrt/reference/timer-class.md)プログレス インジケーターを印刷するクラス。 これらのクラスへの参照を取得するコンス トラクターのバージョンである、 [concurrency::scheduler](../../parallel/concrt/reference/scheduler-class.md)そのスケジュールを設定するオブジェクト。 この例は、フィボナッチ数を計算するタスクをスケジュールする既定のスケジューラと、プログレス インジケーターを出力するタスクをスケジュールするスケジューラ インスタンスを使用します。  
  
 カスタム ポリシーを持つスケジューラを使用する利点を示すため、この例ではタスク全体を 2 度実行しています。 まず、既定のスケジューラを使用して両方のタスクをスケジュールします。 次に、既定のスケジューラを使用して最初のタスクをスケジュールし、カスタム ポリシーを持つスケジューラを使用して 2 番目のタスクをスケジュールします。  
  
 [!code-cpp[concrt-scheduler-policy#1](../../parallel/concrt/codesnippet/cpp/how-to-specify-specific-scheduler-policies_1.cpp)]  
  
 この例を実行すると、次の出力が生成されます。  
  
```Output  
Default scheduler:  
...........................................................................done  
Scheduler that has a custom policy:  
...........................................................................done  
```  
  
 どちらのタスク セットでも結果は同じですが、カスタム ポリシーを使用するバージョンではプログレス インジケーターを出力するタスクを高い優先順位で実行できるため、応答性が向上します。  
  
## <a name="compiling-the-code"></a>コードのコンパイル  
 コード例をコピーし、Visual Studio プロジェクトに貼り付けるかという名前のファイルに貼り付けます`scheduler-policy.cpp`Visual Studio コマンド プロンプト ウィンドウで、次のコマンドを実行します。  
  
 **cl.exe/EHsc scheduler-policy.cpp**  
  
## <a name="see-also"></a>関連項目  
 [スケジューラ ポリシー](../../parallel/concrt/scheduler-policies.md)   
 [方法: スケジューラ インスタンスを管理](../../parallel/concrt/how-to-manage-a-scheduler-instance.md)   
 [方法: 特定のスケジューラ ポリシーを使用するエージェントを作成する](../../parallel/concrt/how-to-create-agents-that-use-specific-scheduler-policies.md)

