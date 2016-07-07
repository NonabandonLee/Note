# Note
iOS-note

- (void)getAllPhotos
{
    ALAssetsLibrary *library = [[ALAssetsLibrary alloc] init];
    // 遍历所有的文件夹, 一个ALAssetsGroup对象就代表一个文件夹
    [library enumerateGroupsWithTypes:ALAssetsGroupAll usingBlock:^(ALAssetsGroup *group, BOOL *stop) {
        // 遍历文件夹内的所有多媒体文件（图片、视频）, 一个ALAsset对象就代表一张图片
        [group enumerateAssetsUsingBlock:^(ALAsset *result, NSUInteger index, BOOL *stop) {
            // 缩略图
//                [UIImage imageWithCGImage:result.thumbnail]);
            // 获得原始图片
//             [UIImage imageWithCGImage:result.defaultRepresentation.fullResolutionImage]);
        }];
        
    } failureBlock:nil];
}




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
