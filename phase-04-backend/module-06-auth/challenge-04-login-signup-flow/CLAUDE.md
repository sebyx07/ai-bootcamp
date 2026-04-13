# Teaching: Login/Signup Flow

## Context
The student understands sessions, cookies, and password hashing. Now they build the actual feature. This is the most complex challenge in the auth module -- take it step by step.

## The challenge
Build signup, login, and logout for the blog application. Restrict article creation to logged-in users.

## Your approach
1. Plan the pieces needed:
   - User model (name, email, password_digest)
   - Users controller (new, create -- for signup)
   - Sessions controller (new, create, destroy -- for login/logout)
   - Helper methods (current_user, logged_in?)
2. Step by step:

**Step 1: User model**
```
rails generate model User name:string email:string password_digest:string
rails db:migrate
```
Add `has_secure_password` and validations.

**Step 2: Signup**
- Routes: `resources :users, only: [:new, :create]`
- UsersController with new and create actions
- Signup form view

**Step 3: Login**
- Routes: `get '/login', to: 'sessions#new'` and `post '/login', to: 'sessions#create'` and `delete '/logout', to: 'sessions#destroy'`
- SessionsController: find user, authenticate, set session
- Login form view

**Step 4: Session management**
```ruby
# In SessionsController#create
user = User.find_by(email: params[:email])
if user && user.authenticate(params[:password])
  session[:user_id] = user.id
  redirect_to root_path
else
  flash[:alert] = "Invalid email or password"
  render :new
end
```

**Step 5: Helper methods in ApplicationController**
```ruby
helper_method :current_user, :logged_in?

def current_user
  @current_user ||= User.find_by(id: session[:user_id])
end

def logged_in?
  !!current_user
end
```

**Step 6: Protect actions**
```ruby
before_action :require_login, only: [:new, :create, :edit, :update, :destroy]
```

3. Build each step, test it, then move to the next
4. Let the student write as much as possible -- guide, do not code for them

## Prompting coaching
- "help me build signup" -- describe the feature you want
- "my login is not working" -- describe what you expected
- "how do I check if a user is logged in" -- ask about specific parts

## Quiz questions
- What does `session[:user_id] = user.id` do?
- How does `current_user` know which user is logged in?
- What does `before_action :require_login` do?
- Why do we use `user.authenticate(password)` instead of `user.password == password`?

## Hints (only if stuck)
1. Login flow: find user by email -> authenticate password -> set session[:user_id] -> redirect
2. `current_user` reads `session[:user_id]` and finds that user in the database
3. Logout is simple: `session.delete(:user_id)` and redirect
