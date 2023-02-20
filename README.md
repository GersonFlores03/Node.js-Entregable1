
# dbdiagram
table users {
  id int [pk, increment]
  name varchar(25) [not null]
  email varchar(30) [unique, not null]
  password varchar(20) [not null, unique]
  age int [not null]
  id_roles int [not null]
}
table teacher {
  id int [pk, increment]
  name varchar(20) [not null]
}
table roles {
  id int [pk, increment]
  name varchar(20) [not null]
}
table categories {
  id int [pk, increment]
  name varchar(20) [not null]
}
table level {
  id int [pk, increment]
  name varchar(20) [not null]
}
table video_course {
  id int [pk, increment]
  title varchar(30) [not null, unique]
  url varchar(35) [not null, unique]
}
table course_general {
  id int [pk, increment]
  title varchar(20) [unique, not null]
  description varchar(50) [unique, not null]
  id_level int [not null]
  id_teacher int [not null]
  id_user int [not null]
  id_categories int [not null]
  id_videos int [not null]
}

Ref: "users"."id_roles" > "roles"."id"

Ref: "course_general"."id_user" > "users"."id"

Ref: "course_general"."id_categories" > "categories"."id"

Ref: "course_general"."id_level" > "level"."id"

Ref: "course_general"."id_teacher" > "teacher"."id"

Ref: "course_general"."id_videos" > "video_course"."id"
# Gerson Elmer Flores Narciso



