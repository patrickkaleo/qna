# DATABASE NAME: webidzfv_qna

### TABLES:
1. user(
    id uuid (with ramsey) primary key,
    email,
    linkedin,
    name (fname + lname)
    password,
    created_at
    email_verified_at
    deleted_at
    school
    profile_verified enum (student, teacher, alumni)
)

2. student(
    user_id foreight key refrences user.id
    grade
)

3. teacher (
    user_id foreign key references user.id
    tag (short tag eg Physics teacher @ Pestalozzi)
    aproved 
)

4. alumni (
    user_id foreign key references user.id 
    class_year (year of graduation)
    curriculum (igcse, ecz, ib) 
    approved 
)

school ( 
    <!-- a list of approved schools on this website  -->
    school id,
    school_name,
    school_location 
)

question (
    id primary key, auto-increment 
    question_tag
    user_id (person who asked the question)
    created_at
    deleted_at 
    grade
    past_paper_desc
    question_body
)

question_tag (
    id
    tag
)

subject(
    id 
    name
)

question_upvote (
    user_id
    question_id
)

question_downvote (
    user_id
    question_id
)

response_upvote(
    question_id
    response_id 
) 

reponse_downvote (
    user_id
    response_id
)

question_likes (
    user_id
    question_id 
)

response_likes(
    user_id 
    response_id 
) 