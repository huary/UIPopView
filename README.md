# UIPopView

一个能自动根据方向显示UIPopView，使用简单，可以找到最为合适的显示方向和区域，可以设置显示方向的优先级，也可以强制只显示在某一个方向上，使用灵活度大，快捷简单

方法1：

    UIPopView *popView = [[UIPopView alloc] initWithPopOverContentSize:CGSizeMake(180, 200)];
    popView.delegate = self;
    popView.dataSource = self;
    [popView popViewFromOverView:sender showInView:toView animated:NO];

方法2：

    CGRect popRect = [sender.superview convertRect:sender.frame toView:toView];
    UIPopView *popView = [[UIPopView alloc] initWithPopOverContentSize:CGSizeMake(180, 200) fromRect:popRect];
    popView.delegate = self;
    popView.dataSource = self;
    [popView popViewFromOverView:sender showInView:nil animated:YES];

方法3：

    UIPopView *popView = [[UIPopView alloc] initWithPopOverContentSize:CGSizeMake(180, 200) fromOverView:sender showInView:toView];
    popView.delegate = self;
    popView.dataSource = self;
    [popView popViewShow:YES];
