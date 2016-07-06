# Note
iOS-note

     UIGraphicsBeginImageContextWithOptions(CGSizeMake(self.frame.size.width, image.size.height * scaleSize), NO, [UIScreen mainScreen].scale);
解决tableView的左滑手势冲突，不灵敏问题
uiscrollview继承UIGestureRecognizerDelegate协议，实现下面方法
-(BOOL)gestureRecognizer:(UIGestureRecognizer *)gestureRecognizer shouldRecognizeSimultaneouslyWithGestureRecognizer:(UIGestureRecognizer *)otherGestureRecognizer
{
    if (gestureRecognizer.state != 0)
    {
        return YES;
    }
    else
    {
        return NO;
    }
} 
