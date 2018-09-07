# GOLANG RECEIVERS

## Declaration
Best Practice is to use pointer receivers since you need to manipulate state
```golang
func (s *Service) PostNote(ctx context.Context, n Note) (Note, error) {
```
