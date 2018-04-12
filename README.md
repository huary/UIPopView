# UIPopView

一个能自动根据方向显示UIPopView，使用简单，可以找到最为合适的显示方向和区域

方法1：

    UIPopView *popView = [[UIPopView alloc] initWithPopOverContentSize:CGSizeMake(180, 200)];
    [popView setColor:WHITE_COLOR];
    popView.delegate = self;
    popView.dataSource = self;
    popView.separatorLineColor = RGB_WITH_INT_WITH_NO_ALPHA(0X666666);
    popView.arrowDirectionPriorityOrder = @[@1];//@[@4,@3,@2,@1];
    [popView popViewFromOverView:sender showInView:toView animated:NO];

方法2：

    CGRect popRect = [sender.superview convertRect:sender.frame toView:toView];
    UIPopView *popView = [[UIPopView alloc] initWithPopOverContentSize:CGSizeMake(180, 200) fromRect:popRect];
    [popView setColor:WHITE_COLOR];
    popView.delegate = self;
    popView.dataSource = self;
    popView.separatorLineColor = RGB_WITH_INT_WITH_NO_ALPHA(0X666666);
    popView.arrowDirectionPriorityOrder = @[@1];//@[@4,@3,@2,@1];
    [popView popViewFromOverView:sender showInView:nil animated:YES];

方法3：

    UIPopView *popView = [[UIPopView alloc] initWithPopOverContentSize:CGSizeMake(180, 200) fromOverView:sender showInView:toView];
    [popView setColor:WHITE_COLOR];
    popView.delegate = self;
    popView.dataSource = self;
    popView.separatorLineColor = RGB_WITH_INT_WITH_NO_ALPHA(0X666666);
    popView.arrowDirectionPriorityOrder = @[@1];//@[@4,@3,@2,@1];
    [popView popViewShow:YES];
