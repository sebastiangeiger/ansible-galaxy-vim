# sebastiangeiger/ansible-galaxy-vim

My vim configuration as a publishable ansible role

## Automated tests

`molecule test`

## Manual tests

`vagrant up && vagrant ssh`

1. `su testing`
2. Password is 'testing'
3. `vim` then type `,t` to ensure fuzzy search comes up
